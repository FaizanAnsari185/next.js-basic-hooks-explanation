I wrote all this in Hindi and then later translated it with the help of Google Translate

1) usePathname
This is a Next.js hook that returns the pathname of the current URL and works only in client-side components.
We will import this from next/navigation
And we will assign this to a variable

"use client"
import { usePathname } from 'next/navigation';

const MyComponent = () => {
    const pathname = usePathname();

    return(
        <h1>
            current path: { pathname }
        </h1>
    )
}

export default MyComponent;


2) useParams
This is a React Hook that is used inside the app router in Next.js. This is used to dynamically extract parameters from the URL.
If our URL is http://localhost:3000/product/123 then 123 is a dynamic parameter. Using useParams we can take this 123 in our component.
If /product/123 then the value of params.id will be 123

To use this, we have to import useParams from next/navigation of Next.js.

And we will assign this to a variable

This only works in client-side components

We have to create a folder inside the app folder with the name product and then inside it we have to create another folder with the name [id] with square brackets and then inside it we have to create page.js and then we can use this

folder Structure ( Route Setup )
📂 app
├── 📂 product
│ ├── 📂 [id]
│ │ ├── 📄 page.js


"use client";
import { useParams } from "next/navigation";

export default function ProductPage() {
  const params = useParams(); // URL se parameter nikalna

  return (
    <div>
      <h1>Product ID: {params.id}</h1>
    </div>
  );
}


output
Product ID: 123


3) useSearchParams
This is a React Hook which is used in the App Router of Next.js. It is used to get and update the query parameters of the URL.

These are written in key:value format
This only works in client-side components
http://localhost:3000/products?category=mobile&brand=samsung
This URL has parameters category and brand
To use this, first we have to import it from next/navigation
Or we will assign it to a variable
Then we can extract the value of category and brand using .get method -- category:mobile, brand:samsung

Folder Structure
📂 app
├── 📂 products
│ ├── 📄 page.js


URL--->  http://localhost:3000/products?category=mobile&brand=samsung

"use client";
import { useSearchParams } from "next/navigation";

export default function ProductsPage() {
  const searchParams = useSearchParams(); // Query parameters lene ke liye

  const category = searchParams.get("category"); // "category" ka value nikalna
  const brand = searchParams.get("brand"); // "brand" ka value nikalna

  return (
    <div>
      <h1>Products Page</h1>
      <p>Category: {category}</p>
      <p>Brand: {brand}</p>
    </div>
  );
}

output-->

Products Page
Category: mobile
Brand: samsung




4) useRouter
This is used to go from one page to another
This only works in client-side components
Should be imported from next/navigation

"use client";
import { useRouter } from "next/navigation";

export default function HomePage() {
  const router = useRouter(); // useRouter ko initialize karna

  const goToProducts = () => {
    router.push("/products"); // "/products" page par le jayega
  };

  return (
    <div>
      <h1>Home Page</h1>
      <button onClick={goToProducts}>Go to Products</button>
    </div>
  );
}
