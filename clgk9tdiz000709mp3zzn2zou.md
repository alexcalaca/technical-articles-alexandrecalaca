---
title: "Rails: How to improve Rails performance with the Russian doll caching technique?"
datePublished: Mon Apr 17 2023 03:22:54 GMT+0000 (Coordinated Universal Time)
cuid: clgk9tdiz000709mp3zzn2zou
slug: rails-how-to-improve-rails-performance-with-the-russian-doll-caching-technique-part-ii
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1681697880665/fd04093f-8532-4cdf-bf1b-d931bf16b7fd.jpeg
tags: programming-blogs, ruby, programming, development, ruby-on-rails

---

### Introduction

This article `How to improve Rails performance with the Russian doll caching technique?` is part II of a series called: "Russian doll caching technique in Rails".

Part II refers to the theory of the topic.

If you did not read Part I, then you should [click here.](https://blog.alexandrecalaca.com/rails-how-to-improve-rails-performance-with-the-russian-doll-caching-technique-part-i)

I hope you enjoy it.

#### Caching

Caching is a critical aspect of performance optimization in any web application, including Ruby on Rails. It can drastically help reduce the number of database queries and HTTP requests, thereby improving response times and reducing server load.

In a Ruby on Rails application, caching can be implemented in various ways, such as page caching, action caching, fragment caching, and HTTP caching. Each type of caching has its specific use cases and benefits, but they all aim to speed up the application and reduce server load.

It's important to keep cache keys consistent and up-to-date with the data being cached. If the cache key becomes stale or outdated, the cache may return incorrect or incomplete data to the user. Therefore, it's essential to use a caching strategy that properly identifies and updates cache keys when the underlying data changes.

#### Role of Developers

As a result, web developers must possess a broad range of technical skills and expertise to build, test, and maintain these complex applications.

We can make our application faster, more scalable, and more responsive to user requests, by using the appropriate caching techniques.

![](https://helios-i.mashable.com/imagery/articles/05y5eGz02le19JXrHwiU1TB/hero-image.fill.size_1200x675.v1626877109.png align="left")

### Russian Doll Caching

#### Why this name?

Russian dolls are also called Matryoshka dolls and nesting dolls. They are a set of wooden [dolls](https://en.wikipedia.org/wiki/Doll) of decreasing size placed one inside another.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1681013661977/b6f00dba-671d-4274-929f-fd1edea3c069.jpeg align="center")

#### Russian Doll Caching in Ruby on Rails

In a Ruby on Rails application, Russian Doll Caching is a technique that involves using nested cache fragments to cache a page's parts hierarchically. It means that each fragment cache depends on its parent fragment cache, which in turn depends on its parent fragment cache, and so on.

The advantage of Russian doll caching is that if a single nested item is updated, all the other inner fragments can be reused when regenerating the outer fragment.

#### How does it work?

When a user requests a page, Rails checks the cache for the top-level fragment cache first. If it's present, Rails returns it to the user. If it's not present, Rails renders the view and caches the top-level fragment. The nested sub-fragments are then rendered, and their corresponding cache keys are derived from the parent cache key.

#### Cache Store

The cache store is used to store and retrieve cached fragments of views. When a view is rendered, each fragment of the view is cached separately in the cache store, with a unique cache key based on the view name and any parameters used to generate the fragment.

When a subsequent request is made for the same view, Rails checks the cache store to see if any of the fragments are already cached. If a cached fragment is found, Rails serves the cached fragment directly from the cache store instead of re-rendering it. This can significantly improve performance by reducing the number of database queries and partial rendering required to generate the view.

The cache store used in Russian Doll Caching must support nested cache keys, such as Redis or Memcached. Rails provides a default cache store based on the file system, but this is not recommended for production use as it does not support nested keys and can be slow for large-scale applications.

#### Cache Keys

In order to allow Rails to retrieve and store the fragment in the cache store, caches need to be identified.

In simple terms, a cache key is a unique identifier for a cache fragment that allows Rails to retrieve and store the fragment in the cache store. Cache keys are used to quickly look up cached data and avoid performing expensive database queries.

So, when a user requests a page, Rails checks if the page is already in the cache using the cache key.

#### Caching Strategy

In Russian Doll Caching in Rails, cache keys play a vital role in determining the caching strategy.

The caching strategy in Russian Doll Caching involves caching nested fragments in a hierarchical manner, using cache keys derived from the object being cached and its associations. This technique allows you to cache complex views with multiple sub-views, each of which can be independently cached.

The nested sub-fragments are then rendered, and their corresponding cache keys are derived from the parent cache key. When the parent fragment is invalidated due to a change in data, all child fragments are also invalidated, ensuring that the cache remains consistent.

This approach allows you to cache a complex view with multiple sub-views, each of which can be independently cached. The resulting cache hierarchy resembles a set of Russian dolls nested inside each other, hence the name "Russian Doll Caching."

![the office meme gifs | WiffleGif](https://78.media.tumblr.com/3f0ab37aab5c0fa87ce340fcfa7b043b/tumblr_pbnncbRE321xx5z6ao1_500.gif align="left")

#### When to Apply

The decision to use Russian Doll Caching or another caching strategy depends on your specific application's needs and requirements. You should consider factors such as \`view complexity\`, \`frequency of data changes\`, \`performance requirements\`, and \`cache storage\` when making your decision.

##### `View complexity`: Russian Doll Caching works much better for complex, nested views that require multiple database queries and partials to render. Another caching method, like as Page Caching or Action Caching, may be more appropriate if your views are comparatively straightforward and don't require numerous database queries or partials.

`Frequency of data changes`: Russian Doll Caching could prove to be a valuable strategy if your application's data changes regularly. Russian Doll Caching allows you to cache fragments at different levels of granularity, so you can avoid re-rendering the entire view when only a small portion of the data has changed.

`Performance requirements:` Russian Doll Caching might be a viable option if your application demands quick response times and high concurrency. By caching fragments and serving them directly from memory, you can reduce the number of database queries and improve application performance.

`Cache storage`: Russian Doll Caching requires a cache store, such as Redis or Memcached, that supports nested keys. If your application is already using a cache store that does not support nested keys, you may need to switch to a different cache store or consider a different caching strategy.

### Conclusion

That's all for today. Thanks for reading the article `How to improve Rails performance with the Russian doll caching technique? Part II.`

If you did not read Part I, then you should [click here](https://blog.alexandrecalaca.com/rails-how-to-improve-rails-performance-with-the-russian-doll-caching-technique-part-i). `Part III` is going to cover the implementation of the Russian doll caching technique in Rails.

I hope this article helped you. Let me know if you have any questions.

Your thoughts, suggestions and corrections are more than welcome.

By the way, feel free to drop your suggestions on new blog articles.

Hope to see you next time.