---
Status: "#knowledge-base"
tags:
  - "#knowledge-base"
  - javascript
  - framework
  - rendering
  - data-fetching
  - hydration
  - server-components
  - client-components
  - fetch-api
  - react
  - nextjs
area: javascript Languages
cover: ReactVsNextjs.excalidraw
type: article
progress: Idea
draft: "false"
title: Understanding Changes from Next 12 to Next 13
---


![[From Next 12 to 13]]
# Next 12 Vs. Next 13

#nextjs #react #rendering #framework #javascript #data-fetching #hydration #server-components #client-components #fetch-api

### Intro

As NextJS has matured over the years, it has gone through some quite significant changes and strong determined actions. 


## Overview
*What does this article consists of*
- [[#Web App Basics]]
- [[#Routing]]
	- Next 13 : [[#App Router]]
	- Next 12 : [[#Page Router]]
- [[#Rendering]]
	- [[#Hydration]]
	- Next 12 : 
		- [[#Static Site Generation (SSG)]]
		- [[#Server Side Rendering (SSR)]]
		- [[#Incremental Static Regeneration]]
	- Next 13 :
		- [[#Static Rendering]]
		- [[#Dynamic Rendering]]
- [[#Components]]
	- [[#Server Components]]
	- [[#Client Components]]
- [[#Data Fetching]]
	- Next 12 :
		- [[#getStaticProps]]
		- [[#getStaticPaths]]
		- [[#getServerSideProps]]
	- Next 13 :
		- [[#generateStaticParams]]
		- [[#Fetch API Next 13]]


## Web App Basics

A web application can be rendered in either of the 2 ways: on the Client's Device or on the Server
With React, web apps are generated on the Client, since NextJS 11, web apps have been made with a hybrid model with some components and pages rendered on client depending on reactive modules on the page or the component or page is rendered on the Server, and then passed to the client to display and interact.


## Routing

### App Router

Ever Since NextJS 13, developers have been given an option to choose between a `page` or an `app` directory during project initiation dialog, selecting the `app` directory uses the new App  Router(recommended). 
### Page Router

A way to route in NextJS . React requires libraries or other methods to provide routing and pages functionality to web apps. Generally React prefers SPA (Single Page Applications). 
With NextJS (until 13) developers were given a page router, which basically is a directory in the source called `pages` . If files or folders>files were added to this directory, it would treat those files as routes (could be redirected to). `pages` also contained an `api` folder which could contain express/node scripts to create an API with your NextJS App.


## Rendering

### Hydration

In Nextjs, most of the pages which can be built are generated statically at build time, then these pre-rendered pages are passed to client to easily and performantly load this data to client device.

After Pre-rendered page is loaded in client side, its JavaScript code is initiated to run any dynamic JS that is needed for full page interactivity on client. 

### Next 12

#### Static Site Generation (SSG)

A way to render websites till Next 12. This would let Nextjs build static pages with available data at build time. These rendered pages are stored at the server and passed to client pre-rendered so client can serve these performantly. 

Content is cached and reused at every step.  

It uses [[#getStaticProps]]

#### Server Side Rendering (SSR)

A way to render websites till Next 12. This would let Nextjs generate HTML at request time, to get fresher data to create the dynamic aspect of the page.  

It uses [[#getServerSideProps]], which is run every time page is requested . 

#### Incremental Static Regeneration

A way to render a page a specific time after generation while in use. After a set amount of time, it re-runs the function to fetch latest data and update the page accordingly. Rules can be set of when and how to refresh.

Set a `revalidate` prop to [[#getStaticProps]] to make it ISR. Subsequent requests are served with most recent cached data till time in `revalidate` is up, then it fetches new data again. 

Available till Next 12. 

![[getStaticProps.png]]


### Next 13

Still renders somewhat similarly than Next 12 but have some changes on when certain things happen, and changed the names of things. 

Default still is [[#NextJS12vNextjs13#Static Site Generation (SSG)|SSG ]] at build time, but now is known as [[#Static Rendering]]

[[#Server Side Rendering (SSR)]] is now changed to **Dynamic Rendering** 

### Static Rendering

Basic Default Rendering in Next13 at build time, and most pre-rendered HTML is cached for future requests. 

#### Dynamic Rendering

Page rendering at requests, in Next 13. Results are not cached.  Basically [[#Server Side Rendering (SSR)]]

Does not require [[#getServerSideProps]], with [[#Dynamic Rendering]] it automatically detects when we have *Uncached Data* or running *Dynamic Functions* (Functions that require information known only at request time, such as cookies, headers or search params)

Its a process of rendering an entire page/route with several components and it repeats this at request, and do all that on the server

Fetch data to render
![[NextDynamicRoute1.png]]
Next switches to dynamic rendering when data is requested/cached
![[NextDynamicRoute2.png]]

## Components

### Server Components

Introduced in Next 13, all Components by default are Server components, i.e executed at the server, not the client. This allows HTML to be pre-rendered on the server. 

Server Components are not hydrated on the client, you can do state or react hooks on these components. They are great for static content, keeping large dependencies or sensitive information away from client

To use interactivity or dynamic content, use [[#Client Components]]

This does not dynamically render an entire page, instead, generates singular components statically on server at build time once, and this page/assortment of components is sent to client at request

### Client Components

Add `use client` on top of any Component to create it as a Client Compoent, this allows the component to use reactivity and interactivity 

These are pre-rendered on the server then hydrated on the client. Only completely rendered on the client, so they can use hooks, listeners and more



## Data Fetching

### Next 12
#### getStaticProps

Till Nextjs 12, used to get data to be acquired for Static Site Generation (SSG) at build time. Typically placed after the Page Component. 

![[NextgetStaticProps.png]]

Gets discontinued in Next 13. Next 13 uses Fetch API to replace this.

#### getStaticPaths

In Next 12 used to generate paths to dynamic routes for eg. blog posts based on blog entries.

Gets discontinued in Next 13. Is now referred to as [[#generateStaticParams]]

Here is an example that uses Posts:

![[NextgetStaticPaths.png]]

#### getServerSideProps

Uses [[#Server Side Rendering (SSR)]] to fetch dynamic data in Next 12 to generate page at request. 

Gets discontinued in Next 13. Next 13 uses Fetch API to replace this.


### Next 13
#### generateStaticParams

Used in Next 13 to generate specific paths based on content. This replaces `getStaticPaths()`

![[NextGenerateStaticParams1.png]]
![[NextGenerateStaticParams2.png]]

#### Fetch API Next 13

Instead of [[#getStaticProps]], we replace it by simple fetch request, and call the data in the page component directly, instead of passing as props (Next 12).
`cache: force-cache` is on by default so we do not need to add that to `getData()`


![[Next13DataFetchStatic.png]]

To use **dynamic content**, and replace [[#getServerSideProps]], we only change the revalidate option to `no-store`. It allows Next to get data on each request and not cache any data from  before. 

![[Next13DataFetchServer.png]]

To use [[#Incremental Static Regeneration]] in Next 13, we add its revalidate clause to fetch api. 

![[Next13DataFetchISR.png]]



### Conclusions










---
# References