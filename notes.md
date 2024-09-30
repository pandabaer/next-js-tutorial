- Pages Router of Next.js might be obsolete
    - App Routing is the new way to go
- Next.js "Middleware" seems to be the way to do HTTP requests, which complies to Web API standards


https://nextjs.org/docs#main-features

Some of the main Next.js features include:

Routing         A file-system based router built on top of Server Components that supports layouts, nested routing, loading states, error handling, and more.
Rendering       Client-side and Server-side Rendering with Client and Server Components. Further optimized with Static and Dynamic Rendering on the server with Next.js. Streaming on Edge and Node.js runtimes.
Data Fetching   Simplified data fetching with async/await in Server Components, and an extended fetch API for request memoization, data caching and revalidation.

https://nextjs.org/learn/dashboard-app



# styling

* tailwind or css modules

Problem with plain CSS. If you define styling classes and you change them,
it's hard to figure, which components use them and whether you broke something


# image optimization

Image optimization features:

* Preventing layout shift automatically when images are loading.
* Resizing images to avoid shipping large images to devices with a smaller viewport.
* Lazy loading images by default (images load as they enter the viewport).
* Serving images in modern formats, like WebP
  and AVIF
  , when the browser supports it.

# Routing

## Layout

some part of the page, that is common across different routes (URL paths or in Next.js-lingo: "pages").
May contain:
* header
* footer
* sidebar

The components from the page.tsx files will be rendered as a child of the "layout".

The "layout" won't rerender, when going to a sub-page (partial rendering).

Also mind the `RootLayout`, which was used to add global styles.

## Links

Why optimize links? A regular `<a href="...">` leads to a full page refresh!
With `<Link>` you only load the `page` part.

Next.js does code splitting by routes, so it does not ship the full app, when the root page is opened (as a normal React SPA would do). This also means that if a certain page throws an error, the rest of the application will still work.

Furthermore, in production, whenever `<Link>` components appear in the browser's viewport, Next.js automatically prefetches the code for the linked route in the background.

