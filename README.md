# boring technology

* has been around
* just works
* has a future
* [makes simple easy](https://www.youtube.com/watch?v=SxdOUGdseq4) (avoids accidental complexity)

boring technology is [a shark, not a dinosour](https://www.simplethread.com/relational-databases-arent-dinosaurs-theyre-sharks/).

this page has an approach for evaluating the boringness of technologies.

## bts

bts is the boring technology score. you calculate bts by multiplying the following factors:

* longevity (<5 years = 0, 5 years = 0.1, 6 years = 0.15, 10 years = 0.5, 20 years = 1.0)
* accidental complexity (0.1 = extremly high - typically more than 10 deployed components, 0.5 = medium - typically more than 5 deployed components, 0.7 = low - typically more than 3 deployed components, 0.9 - very low - typically less than 3 deployed components)
* works and has community (1 = &gt;50k, 0.5 &gt;10k, 0.2 &gt;1k, 0.1 &lt;1k github stars)
* activity (1 = last merge within a week, 0.5 = last merge within a month, 0.1 = last merge within a year)

## extremely boring technology stack

*extremely boring technology stack* is an opinionated technology stack that works for a
surprisingly large number of use cases. the accidental complexity is minimized by [just using
postgres for everything](https://www.amazingcto.com/postgres-for-everything/), using 
multi-page app for almost everything, and when that fails, using
[hypermedia-driven architecture](https://htmx.org/essays/hypermedia-driven-applications/).

|technology|name|bts|replaces|comments|
|---|---|---|---|---|
|backend|django||fastapi, flask|you will quickly outgrow the simplistic solutions, just use a basic django template|
|frontend|django||REST + react/vue|use admin where possible, mpa for all user views, and htmx/alpine when that does not work|
|database|postgres||sqlite, mysql|while postgres is more complex than sqlite, it has features allowing you to avoid other components
|background tasks| django-tasks|| celery| celery established, but it is too complex
|caching|django||redis|use plain django caching for basic needs. for 'webscale' caching, use django-distill + s3 + cdn
|full-text search|postgres||elastic|
|queue|postgres||rabbitmq, kafka|postgres queues can be used to get ACID properties
|periodic running|superchronic||cron|version for cron that runs in docker container
|multi-process|honcho||systemd, k8s|running multiple things inside one paas contaoiner
|dependencies|pip||poetry, uv|uv looks promising, but so did poetry
|deployments|docker + paas||k8s|just use a paas, such as fly.io

## about

i do django consulting,

contact me at mikko at boringtechnology dot org
