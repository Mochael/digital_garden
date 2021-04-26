---
title: What is Next.js
tree_state: 🌱
---

Useful article on Next.js: https://www.smashingmagazine.com/2021/04/incremental-static-regeneration-nextjs/

**Next.js** is an open-source React framework for server side rendering your pages. It's pretty versatile and is popular in settings from JAMstack to conventional dynamic webapps.

Jamstack (see [[What is JAMStack]]) is super useful if your content changes very infrequently, because you might be stuck waiting hours for your site to build. If we have a sight like Amazon that has constantly updating products, it would be chaos to try to rebuild it after every update. So Next.js came and introduced Incremental Static Regeneration (ISR), which allows you to update static content instantly without needing a full rebuild of your site. You can choose to use static-generation on a per-page basis, without needing to rebuild the entire site.

Comparing it to Gatsby: Gatsby is a static site generator, without a server. You build the site, and then you deploy the result of the build process statically on Netlify or another static hosting site. Next.js provides a backend that can server side render a response to request, allowing you to create a dynamic website, which means you will deploy it on a platform that can run Node.js. Next.js is also useful to generate a completely static site though.
