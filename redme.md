I wrote all this in Hindi and then later translated it with the help of Google Translate

1) usePathname
This is a Next.js hook that returns the pathname of the current URL and works only in client-side components.
We will import this from next/navigation
And we will assign this to a variable

2) useParams
This is a React Hook that is used inside the app router in Next.js. This is used to dynamically extract parameters from the URL.
If our URL is http://localhost:3000/product/123 then 123 is a dynamic parameter. Using useParams we can take this 123 in our component.
If /product/123 then the value of params.id will be 123

To use this, we have to import useParams from next/navigation of Next.js.

And we will assign this to a variable

We have to create a folder inside the app folder with the name product and then inside it we have to create another folder with the name [id] with square brackets and then inside it we have to create page.js and then we can use this

This only works in client-side components

3) useSearchParams
This is a React Hook which is used in the App Router of Next.js. It is used to get and update the query parameters of the URL.

These are written in key:value format
This only works in client-side components
http://localhost:3000/products?category=mobile&brand=samsung
This URL has parameters category and brand
To use this, first we have to import it from next/navigation
Or we will assign it to a variable
Then we can extract the value of category and brand using .get method -- category:mobile, brand:samsung

4) useRouter
This is used to go from one page to another
This only works in client-side components
Should be imported from next/navigation