# Tailwind CSS

- a framework with utility classes.
- used for styling webpages
- lower level than Bootstrap, it provides low level utility classes which provides a granular level control over components.
- more flexible
- provides a unique look to your website unlike Bootstrap


```shell
npm init -y
npm install tailwindcss
npm install --save-dev live-server
mkdir src;
# Add components into src/styles.css and execute tailwind build command to create css file in public directory.
npm run build
```

## Colors
- `bg-red-500` applies background red 500
- `container`: create container
- `mx-auto`: X margin auto
- `w-` set the width of the element. There are multiple classes. Please refer to docs.
- `h-` set the height of the element.

## Flex
- `flex` set the inner elements in horizontal fashion
- `flex flex-col` set the elements in vertical fashion, on top of each other.
- `flex flex-col-reverse` arrange elements in reverse
- `flex flex-row-reverse` arrange elements right aligned but in horizontal fashion
- `flex flex-wrap` wrap the flex items when size is below their needed width.
- `flex flex-wrap-reverse` This will wrap in reverse order. First element go to the bottom if size reduces required width.
- `flex-1` This is added to flex items and this will make flex items extend for larger window sizes. this will ignore assigned sizes using `w-` classes.
- `flex-initial` added to flex items. It will allow the flex items to reduce in size but will consider the assigned size.
- `flex-auto` to all flex items. This will allow items to shrink and grow and will also consider the initial assigned width.
- `flex-none` will not allow flex items to grow nor shrink.
- `flex-grow` will allow flex items to grow
- `flex-grow-0` will not allow flex items to grow, it will allows to shrink
- `flex-shrink-0` will not allow to shrink
- `order-1` will place flex item as first item and similarly second and third.

## Grid
- `grid` create a grid
- `grid grid-cols-3` create grid of 3 columns
- `gap-4` add 4 gap between grid elements horizontally and vertically.
- `col-span-2` span grid element by 2 columns
- `grid grid-rows-3` create row grid
- `grid grid-rows-3 grid-flow-col` create placement of rows in column wise. `grid-flow-*` defines how the elements of grid are placed.
- `row-span-2` will span grid element by 2 rows
- `gap-x-4` create gap only in x direction
- `gap-y-4` create gap between rows only.
- `justify-items-end`: justify and place items at the end (on the right side).
- `justify-items-start` justify items on the left
- `justify-items-center` place items on the center
- `justify-items-stretch` will stretch item automatically to available width.
- `justify-self-*` These properties can also be assigned to items in the grid. This helps customize grid items individually.

## Margin and Padding
- `m-10` apply margin to an element on all sides.
- `mt-10` apply margin from the top only.
- `ml-10` apply margin from the left only
- `mr-10`
- `mb-10` apply margin from the bottom.
- `p-10` apply padding to element from all sides.
- `pt-10` apply padding only on top. Similarly it has `pl`, `pr` and `pb` classes just like margin classes.

## Text Styling
- `text-sm` make text small
- `text-xs` make text extra small
- `text-base` make text regular size
- `text-lg` make text large
- `text-xl` make text extra large
- `text-2xl` make text 2 times larger than XL
- `italic` make text italic
- `font-thin` make font thinner
- `font-extralight` make font extra light
- `font-light` make light font
- `font-normal`
- `font-medium`
- `font-bold` make font bold
- `font-extrabold`
- `font-semibold`

- `text-right` make text right aligned
- `text-center`
- `text-left`

- `text-transparent` make text transparent
- `text-white` make text white
- `text-black` make text black
- `text-blue-500` make text blue

- `text-opacity-100` set text opacity to 100. totally visible
- `text-opacity-10` set text little opaque.

- `uppercase` make text uppercase
- `lowercase`
- `capitalize` capitalize text
- `normal-case` normal text

## Border

- `rounded` make slightly rounded border
- `rounded-sm`: less rounded
- `rounded-md`: medium rounded
- `rounded-lg`: large round
- `rounded-xl`
- `rounded-2xl`
- `rounded-full`: make button more like a circular on both left and right
- `rounded-t-md`: make top side rounded only
- `rounded-b-md`: make bottom side rounded only
- `rounded-l-md`: make left side rounded only
- `rounded-r-md`: make right side rounded only

- `border-4`: make border 4px
- `border-0`: no border
- `border-8`: border 8px on all sides
- `border-r-8`: only right side border of 8px
- `border-t-8`: top border 8px only
- `border-b-8`
- `border-l-8`: only set left side border of 8px

- `border-red-200`: set red color border
- `border-blue-800`: darker blue border
- `border-opacity-100`: make border appear cleanly
- `border-opacity-0`: make border invisible
- `border-opacity-50`: make border slighly visible

- `border-dashed`: make dashed border
- `border-dotted`: make border dotted
- `border-double`: make double border around element

- `shadow`: add shadow on all sides
- `shadow-xl`: make extra large shadow
- `shadow-none`: no shadow
- `shadow-inner`: set shadow inside element

## Breakpoints
- `2xl:text-pink-500`: set text color to pink for 2 extra large devices. The default device sizes are defined in [this doc](https://tailwindcss.com/docs/responsive-design#using-custom-breakpoints).
- `xl:text-yellow-500`: set text color yellow for extra large devices.
Similarly other properties can also be customized based on device sizes.

## Pseudo Selectors
Change behavior based on mouse or user actions using pseudo selector
- `hover:bg-blue-400`: change color when user hovers over to blue color
- `hover:text-white`: change also color of text to white
- `focus:bg-white-500` on focus, change background color to white
- `group`: applied to parent element
- `group-hover:text-white`: applied to child element. When parent is hovered, it will change the style of child element to which this class is applied.

## Directives
`@tailwind` is the directive and the `base` directive have all simple styles. To changes default styles, we change the layers in `src/styles.css` file rather than `public/styles.css` file. For example, to alter elements of `base` class, we use `@layer` like below.

```css
@layer base {
    a {
        @apply text-green-500;
    }
}
```

This will require rebuild of the code so that new styling gets applied.

## Components

If we have to have same styling to two buttons for example, we have to repeat same code except button text. In such cases, to avoid repeatitions, we can define component using `@layer`.

```css
@layer components {
    .menu-button {
        @apply text-white bg-indigo-500 p-3;
    }
}
```

Then rebuild the project and then inside the HTML file, we could use  

```html
<button class="menu-button">click</button>
```

## Extra Utilities class
Change utilities classes using layer and change default behavior of the available class.

```css
@layer utilities {
    .text-green-500 {
        color: blue;
    }
}
```

When we use the `@apply` directive, we 

```css
.menu-button{
    @apply text-white bg-green rounded;
}
```

When we rebuild, we get some new CSS generated even if we have removed available layers. Next time, when we create a button with available `menu-button` class, all the styles get applied.
Similarly, `@layer` is applied to change the contents of available classes. For that we use `@layer` to access available class and then we use specific element and `@apply` our defined classes to change the behavior.
To create components, we have to access `components` layer using `@layer components`. Similarly, utility classes such as `bg-green-500` can be modified using `@layer utilities` and change the behavior of utilities class.

