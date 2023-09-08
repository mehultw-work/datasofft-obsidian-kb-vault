---
Status: "#knowledge-base"
tags:
  - "#knowledge-base"
  - javascript
  - framework
  - language
  - react
  - nextjs
area: javascript Languages
published: "false"
cover: ReactVsNextjs.excalidraw
type: article
progress: Idea
---
![[ReactVsNextjs.excalidraw]]
# ReactJS vs NextJS

#javascript #framework #nextjs #react #language 


### Intro


Here we will explore the differences between React and Next.js, focusing on topics such as client and server components, hydration strategies, and rendering. Let's dive in!

### Context


NextJS is a meta-framework which builds on top of React. It uses React under the hood with modern implementations so users don't have to concern themselves with default boilerplates to start an application.

NextJS prefers Server side components to help provide better SEO to the end-user, since most client side components have content fetched from the server and only the already built HTML reaches client, effectively reducing the bundle size.

Other than being a Client Side Application, NextJS allows you to create sophisticated back-end code using NodeJS and publish APIs right from the same application. This allows Nextjs to function as a Full Stack Framework. 

> *Even the creators of React agree that developers should choose one of React's Meta frameworks to build modern applications and websites.*


## Overview

- [[NextJs vs React#Intro|Intro]]
- [[NextJs vs React#Context|Context]]
- [[NextJs vs React#1. Client and Server Components|Client/Server Components]]
- [[NextJs vs React#2. Hydration Strategies|Hydration Strategies]]
- [[NextJs vs React#3. Routing|Routing]]
- [[NextJs vs React#4. Data Fetching|Data Fetching]]
- [[NextJs vs React#5. SEO Considerations|SEO]]
- [[NextJs vs React#6. Deployment|Deployment]]
- [[NextJs vs React#Thoughts|Thoughts]]
- [[NextJs vs React#Conclusions|Conclusions]]




#### 1. Client and Server Components

React: React primarily uses client-side rendering (CSR), where the UI elements are generated on the browser using JavaScript.

Next.js: Next.js utilizes server-side rendering (SSR), also known as pre-rendering. The content on the web is generated on the server and sent to the client already rendered.
This allows Next.js to use a hybrid approach to rendering, by allowing components to render either on the server or the client depending on use case and developer choice.

#### 2. Hydration Strategies

React: React uses hydration to attach event handlers and update the DOM to match the virtual DOM after the initial render. This allows for interactivity and dynamic updates on the client-side. When a change occurs in the application's state, React calculates the minimal number of updates required and applies them to the virtual DOM before rendering the changes to the actual DOM. The entire code bundle is forwarded to client and client builds the page upon requests.
React uses client-side hydration to attach event listeners and enable interactivity after initial HTML rendering. This can sometimes lead to a flash of unstyled content (FOUC) or other rendering issues.

Next.js: Next.js extends React by introducing server-side rendering (SSR) and static site generation (SSG). SSR allows React components to be rendered on the server and sent as HTML to the client, which can significantly improve initial page load times. SSG pre-builds entire pages at build time, making them incredibly fast to load.
Next.js optimizes hydration with the next/script package. It allows you to control when and how scripts are loaded, reducing FOUC and improving performance.
#### 3. Routing

React: In React, you need to use a library like React Router to handle routing and orchestrate transitions between pages.

Next.js: Next.js simplifies routing by integrating it directly into the pages folder. Routes are built into the pages, making it easier to navigate between different pages.
APIs can be created by adding node files to the `pages/api` directory 
Next.js 13 utilizes a new way to create routes using the `app` directory, more on that in [[NextJS12vNextjs13]] 
#### 4. Data Fetching

React: React allows you to fetch data from APIs using libraries like Axios or the built-in Fetch API. You can use lifecycle hooks like `useEffect` to handle data fetching and updating the component state.

Next.js: Next.js provides built-in data fetching methods like `getStaticProps` and `getServerSideProps` for pre-rendering data on the server. These methods allow you to fetch data before rendering the page, **improving performance and SEO.**


###### React Data Fetching Example
```js
// React example
import React from 'react';
import { useEffect, useState } from 'react'

const MyComponent = () => {
  const [data, setData] = React.useState(null);

  React.useEffect(() => {
    // Fetch data from API
    fetch('https://api.example.com/data')
      .then(response => response.json())
      .then(data => setData(data))
      .catch(error => console.log(error));
  }, []);

  return (
    <div>
      {data ? (
        <ul>
          {data.map(item => (
            <li key={item.id}>{item.name}</li>
          ))}
        </ul>
      ) : (
        <p>Loading...</p>
      )}
    </div>
  );
};

export default MyComponent;
```


###### NextJS data fetching example

```js

// Next.js example
import React from 'react';

const MyComponent = ({ data }) => {
  return (
    <div>
      {data ? (
        <ul>
          {data.map(item => (
            <li key={item.id}>{item.name}</li>
          ))}
        </ul>
      ) : (
        <p>Loading...</p>
      )}
    </div>
  );
};

export async function getStaticProps() {
  // Fetch data from API at build time
  const response = await fetch('https://api.example.com/data');
  const data = await response.json();

  return {
    props: {
      data,
    },
  };
}

export default MyComponent;

```

#### 5. SEO Considerations

React: React relies on client-side rendering, which may result in slower initial page loads and difficulties in search engine indexing due to the reliance on JavaScript for rendering content.

Next.js: Next.js offers server-side rendering (SSR), generating fully rendered HTML pages on the server. This improves initial page load times and ensures better search engine indexing, enhancing SEO performance.


#### 6. Deployment

React: React applications can be deployed on various platforms, including static file hosts, content delivery networks (CDNs), and cloud hosting providers.

Next.js: Next.js provides a streamlined deployment process and integrates easily with CI/CD pipelines. It is well-suited for static sites and can be deployed on platforms like Vercel, Netlify, or AWS Amplify.


### Thoughts 

These are just a few of the differences between React and Next.js. React offers a versatile library with more control over implementation, making it suitable for custom components and flexible applications. Next.js, on the other hand, provides a framework with features like server-side rendering and automatic code splitting, making it ideal for static sites and rapid development.



### Conclusions

Remember to consider your project requirements, performance implications, SEO considerations, and deployment options when choosing between React and Next.js. 

In summary, React and Next.js are both powerful tools for building web applications, but they cater to different needs. React is a flexible library suitable for a wide range of applications, while Next.js is a framework that simplifies the development of server-rendered React applications with a focus on performance and SEO.

The choice between React and Next.js depends on your project's requirements. If you need server-side rendering, SEO optimization, and a structured framework, Next.js is an excellent choice. If you prefer flexibility and are building a single-page application or have unique project requirements, React might be the better option.

Ultimately, both React and Next.js have their strengths, and the right choice depends on your specific use case and development preferences.








---
# References

