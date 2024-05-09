---
title: 'The Migration Adventure: CRA to Vite and npm to pnpm'
description: 'A little snippet about my journey of migrating a project from create-react-app to Vite and from npm to pnpm and the challenges of making these changes at once.'
canonicalUrl: "https://mohamedyamani.com/blog/the-migration-adventure-cra-to-vite-and-npm-to-pnpm/"
pubDate: 2023-07-05
image: "/images/thumbnails/the-migration-adventure-cra-to-vite-and-npm-to-pnpm.jpg"
imageAlt: "purple and white abstract painting"
---

As I was migrating a client's project from CRA to Vite I encountered plenty of issues. Some of which were due to certain imports that are specific to Webpack, the other ones were due to me using `pnpm` as opposed to `npm`.

That wasn't a smart move, migrating to another build tool as well as another package manager at once. So I switched back to using `npm` to finish my Vite migration, fixed the errors, all good.

When I tried using `pnpm` again and installed the packages using it, it kept throwing many errors that package X, Y, Z are not installed, which is weird, because the `npm` version works just fine!

Via `pnpm import`, the existing lock files are parsed and `pnpm-lock.yaml` gets generated, so the lock files should have the same content.

It is true that all the dependencies that are mentioned in the lock files will be installed by `pnpm` without fault. However, due to how `npm` installs packages and their dependencies, you will find yourself being able to use a dependency of a package without explicitly installing.

That's exactly what happened, notably with `date-fns` and some other packages. How `npm` structures your `node_modules/` allows you to import `date-fns` even if it wasn't present as a dependency in your `package.json`, as long as some other package depends on it.

Bottom line, explicit is better than implicit.

I downloaded the missing packages like a good boy and life moved on 🙂.

## References

I followed [this article](https://www.robinwieruch.de/vite-create-react-app/) to switch from CRA to Vite, it was very helpful.

---

Thumbnail picture by [FlyD](https://unsplash.com/@flyd2069?utm_content=creditCopyText&utm_medium=referral&utm_source=unsplash) on [Unsplash](https://unsplash.com/photos/purple-and-white-abstract-painting-3TtVnxJHfhw?utm_content=creditCopyText&utm_medium=referral&utm_source=unsplash)