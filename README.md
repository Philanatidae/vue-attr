# vue-attr
Insert attributes into rendered HTML from Vue

## Introduction
While using Vue with custom elements, I noticed that the ```slot``` attribute was not working correctly. Upon further inspection, it appeared that Vue was absorving the ```slot``` attribute regardless of whether a parent node had a ```<slot>``` tag with the same name of the ```slot``` attribute. I created this Vue directive as a quick, temporary fix until the issue can be corrected within Vue.

## Installation

### npm
You can install vue-attr with npm:

    npm install vue-attr

You can then import it:

    var VueAttr = require('vue-attr')
    Vue.use(VueAttr);

Or, using ES6 imports:
    import VueAttr from 'vue-attr'
    Vue.use(VueAttr);

### Direct include
If you have Vue included globally, you can include vue-attr with a ```<script>``` tag and it will install itself (you can do this by downloading the files directly or by using bower).

## Usage
vue-attr includes the ```v-attr``` directive, which can be attached to an attribute:

    <div v-attr:slot="'example'">
        <!-- Rendered HTML will be <div slot="example"></div> -->
    </div>

One note to consider is that the value of the directive must be a JavaScript literal, hence the single quotes in the above example. vue-attr *will* work by just placing in the value of the attribute, but Vue will spout errors warning you that your value is not a property of the component. The side effect of this is that if you have a property with the same name, the property value will be bound to the attribute's value (similar, in some ways, to v-bind). It is best practice to use JavaScript literals instead.

## License
[Unlicense](http://unlicense.org/)