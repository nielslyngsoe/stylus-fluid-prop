## Stylus-Fluid-Prop
> Stylus Fluid Properties — make your properties scale fluidly

For SASS version look here: https://github.com/nielslyngsoe/sass-fluid-prop


#### Description:

FluidProp can be used to define a property value with one or several linear interpolations controlled by the viewport width.


#### Example:

```
html {
   
   FluidProp-start('font-size', 320, 7);
   FluidProp-step(1024, 10);
   FluidProp-step(1600, 12);
   FluidProp-end();
   
}
```

In this example we are setting the font-size on the html element.
This setup will result in the font-size begin 7px when the viewport-width is between 0px and 320px.
Between 320px and 1024px the font-size will grow linear from 7px to 10px.
As well the font-size will grow from 10px to 12px from viewport-width 1024px to 1600px.
When the users viewport-width has reached 1600px the font-size will stay at 12px.


#### Example with endless growth:

```
h1 {
   
   FluidProp-start('font-size', 320, 7);
   FluidProp-step(1024, 10);
   FluidProp-step(1600, 12);
   FluidProp-endless(.04);
   
}
```

In this example the font-size will growth endlessly from a viewport-width of 1600px and up.
From 1600px the font-size will grow with 4% of the viewport-width growth, meaning that at a viewport-width of 1700px the font-size will be 16px (cause 4% of 100px is 4px).


#### Example with other property types:

```
h1 {
   
   FluidProp-start('margin-left', 320, 10);
   FluidProp-step(1024, 20);
   FluidProp-step(1600, 40);
   FluidProp-endless(.04);
   
}
```

This example shows that you can use any property type with FluidProp.
