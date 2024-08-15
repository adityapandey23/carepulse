## Introduction
___
* In this we'll setup the project locally in order to maximize the efficiency


### Step-1
___
* Create a simple Next.js app using 
``` Bash
npx create-next-app@latest ./
```
* Clean up the existing code

### Step-2
___
* Change the font to `Plus_Jakarta_Sans` in the `layout.tsx` file
* We can also add stuff like `weight` and we can also add a `variable` 
``` Typescript
const fontSans = Plus_Jakarta_Sans({
	subsets: ["latin"],
	weight: ["300", "400", "500", "600", "700"],
	variable: "--font-sans",
});
```


### Step-3
___
* Install the following stuff
``` Bash
npm install clsx tailwind-merge
```
* `clsx` -> merge class names conditionally
* `tailwind-merge` -> merge tailwind class names
* Adding some of the utility classes by creating a new folder in the root by the name of `lib` which has a file of `utils.ts`, inside this we can mention all the utility classes
* Example for the `cn` function
``` Typescript
export function cn(...inputs: ClassValue[]) {
	return twMerge(clsx(inputs));
}
```

``` Typescript
className={cn(
	"min-h-screen bg-dark-300 font-sans antialiased",
	fontSans.variable
)}
```
	This will indicate that whenever we use the fontSans.variable, the following classes will get merged and be applied

* Also we'll add some stuff to the `global.css` and `tailwind.config.ts`
* We'll also have to install 
``` Bash
npm install tailwind-animate
```


## Step-4
___
* Follow the docs of `Shadcn` to get started
* It is possible that the stuff get's overwritten so make sure to copy `global.css` and `tailwind.config.ts` once again
* After this make sure to wrap our app in the theme provider