# Vue.js BEM Directive

If you find yourself writing a lot of long, tedious CSS class names in
order to be consistent with the BEM naming convention, then try this
directive. It automagically does all the heavy lifting based on
the component's name found in $options.name.

It can produce BEM classes similar to those Harry Roberts advocate in
[this article](http://bit.ly/1R3nlNG).

With that said, if you write this:
```
<div v-bem:,premium v-bem:o-media.block>
 <img src="" alt="" v-bem:photo v-bem:o-media,img.block v-bem:c-avatar.block />
 <p v-bem:bio v-bem:o-media,body,large.block>...</p>
</div>
```

It produces:
```
<div class="o-media c-user c-user--premium">
 <img src="" alt="" class="o-media__img c-user__photo c-avatar">
 <p class="o-media__body c-user__bio">...</p>
</div>
```

A different example with a more tedious component name like
'congratulations-card':
```
 <div v-bem>
   <section v-bem:content>
     <div v-bem:title>{{ title }}</div>
     <p v-bem:message>{{ message }}</p>
   </section>    
   <footer v-bem:footer>
     <slot name="footer"></slot>
   </footer>
 </div>
```

Produces:
```
<div class="c-congratulations-card">
 <section class="c-congratulations-card__content">
   <div class="c-congratulations-card__title"></div>
   <p class="c-congratulations-card__message"></p>
 </section>    
 <footer class="c-congratulations-card__footer"></footer>
</div>
```