---
id: features-metadata
title: Next.js - Meta Data
sidebar_label: Next.js - Next.js - Meta Data
sidebar_position: 3
tags: [Next.js Features Pages]
description: "In this section, you will learn about Features of NEXT ."
---
## Next.js - Meta Data

In Next.js, we can serve modify the head section of each react pages very easily with the help of ```<Head>``` react component which is inbuilt.

Let's update the nextjs project used in Pages chapter.

Update index.js as follows −

```
import Link from 'next/link'
import Head from 'next/head'

function HomePage() {
   return (
      <>
         <Head>
            <title>Welcome to Next.js!</title>
         </Head>
         <div>Welcome to Next.js!</div>
         <Link href="/posts/first"><a>First Post</a></Link>
         <br/>
         <img src="/logo.png" alt="TutorialsPoint Logo" />
      </>	    
   )
}

export default HomePage
```

Update first.js as follows −

```
import Link from 'next/link'
import Head from 'next/head'

export default function FirstPost() {
   return (
      <>
      <Head>
         <title>My First Post</title>
      </Head>
      <h1>My First Post</h1>
      <h2>
         <Link href="/">
            <a>Home</a>
         </Link>
      </h2>
      </>	  
   )
}
```

Here we've added a reference to logo.png in index.js file.

Start Next.js Server
Run the following command to start the server −.

```
npm run dev
> nextjs@1.0.0 dev \Node\nextjs
> next

ready - started server on http://localhost:3000
event - compiled successfully
event - build page: /
wait  - compiling...
event - compiled successfully
event - build page: /next/dist/pages/_error
wait  - compiling...
event - compiled successfully
```


## Verify Output

Open localhost:3000 in a browser

<BrowserWindow>
       <div id="output_con_1">
            <h1>Welcome to Next.js!</h1>
            <h2 onClick={()=>{
               let output_con_1=document.getElementById("output_con_1")
               output_con_1.style.display="none"
               let output_con_2=document.getElementById("output_con_2")
               output_con_2.style.display="block"
            }} style={{color:"blue",textDecoration:"underline",cursor:"pointer"}}>First Post</h2>
            <img src="/img/favicon_io/android-chrome-192x192.png" alt="CodeHarborhub Logo" style={{height:"5rem",width:"5rem"}} />
       </div>
       <div style={{display:"none"}} id="output_con_2">
            <h1>My First Post</h1>
            <h2 onClick={()=>{
               let output_con_2=document.getElementById("output_con_2")
               output_con_2.style.display="none"
               let output_con_1=document.getElementById("output_con_1")
               output_con_1.style.display="block"
            }} style={{color:"blue",textDecoration:"underline",cursor:"pointer"}}>Home</h2>
       </div>
</BrowserWindow>