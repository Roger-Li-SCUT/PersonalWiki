## JSX Spread Attributes [Back](./../react.md)

If you know all the properties that you want to place on a component ahead of time, it is easy to use JSX:

{%ace edit=false, lang='jsx', theme='tomorrow' %}
var component = <Component foo={x} bar={y} />
{%endace%}

It's bad to mutate props like this:

{%ace edit=false, lang='jsx', theme='tomorrow' %}
var component = <Component />
component.props.foo = x;    /** bad */
component.props.bar = y;    /** also bad */
{%endace%}

This is an anti-pattern because it means that we can't help you check the right propTypes until way later. This means that your propTypes errors end up with a cryptic(含義隱晦的) stack trace.

The props should be considered immutable. Mutating the props object somewhere else could cause unexpected consequences so ideally it would be a frozen object at this point.

### Spread Attributes

**Spread Attributes** has used a new operator, `...` notation, in ES6, and this is a new feature of jsx.

As firstly, we know atributes `foo`, but not `bar`, and we can extend it like this:

{%ace edit=false, lang='jsx', theme='tomorrow' %}
var props = {};
props.foo = x;

/** spread attributes: ...props */
var component = <Component {...props} bar={y} />
{%endace%}

If we also extend `foo`, it will be overrided.

{%ace edit=false, lang='jsx', theme='tomorrow' %}
var props = {};
props.foo = x;

/** spread attributes: ...props */
var component = <Component {...props} foo={'overriden'} />

console.log(component.props.foo);   /** => overriden */
{%endace%}



