Intro
- rails 4.0.0.rc1 available
- patterns of basecamp's application architecture
- rails/basecamp interlinked
- good frameworks are extractions, not inventions
- what would someone somewhere might want to do?
  - running away from tool-builders (don't match real-world development)
- other people are tackling the same problems as me
- 10 years
  - state of the art has changed
- people lock their expectation of hardware/scarce resources to when they started programming
- java/struts gone (though jvm lives on)
- pioneering spirit sets ruby/rails apart from frameworks before it
  - community willing to sacrifice for progress
- rails 2.3 released 4 years ago (2009)
- "Good software takes ten years. Get used to it" - Joel Spolsky
- New contributors with their first commit to rails (from 40 in 2004 to >500 in 2012)
- Crossed the chasm (roger's innovation adoption curve)

Purpose
- What is the purpose?
- Big tent: room for a lot of different people (merb as an example in rails 3)
- Don't be a ferris wheel.  Can't be everything to everyone all the time.

Context
- Dynamic hypertext documents (context of basecamp)
- Grandness in embracing simplicity
  - hypertext markup language is more than just a delivery mechanism
- Contiuum of applications
  - Wikipedia (document)
  - Spotify (GUI)
- Where does something like google maps fit?  Not related to documents (on the surface)

Information Technology
- Constraints are liberating
- Java applets (as a failure example)
- Flash (remove web's contraints)
- Silverlight
  - Free you from HTML!
  - Use a better language, and all your problems will be solved
  - Didn't pan out, HTML won out again
- iOS
  - Games are the top downloads (along with fart apps)

Embrace the Document
Evolve the Document

What people like about native solutions?  Speed.  "We want native stuff because we want fast stuff"

Can we get speed without throwing out everything we have?

Five patterns embraced for basecamp

- Key-based cache expiration
  - or generational caching
  - rails - every instance has a cache key - move away from sweepers
  - need a least-recently-used cache (memcache or redis in LRU mode)
- Russian-doll nested caching
  - touching (belongs_to :model, touch: true)
  - included in rails4
  - gem: cache-digests
- JavaScript decoration of shared caches
  - how do you show times without caching a single users timezone
  - <time> tag, store the utc time as an attribute on the tag and display the actual value
  - caching user-specific actions (things that change based on permissions, etc)
  - Show the link to everyone, but decorate with html5 data attributes that hand off to javascript for display
    - i.e. link_to "Edit", ... { "data-visible-to" => "admin creator" }
- Turbolinks process persistence
  - based on pjax (pushState + ajax)
  - 20-70% speed increase
- Polling for javascript updates
  - page_updates, local_page_updates, remote_page_updates
  - 1 redis instance, 6 rainbow workers, 100K RPM (http://rainbows.rubyforge.org/FAQ.html)












