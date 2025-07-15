# boring technology

boring technology 
* has been around
* just works
* has a future
* avoids accidental complexity

boring technology is [a shark, not a dinosour](https://www.simplethread.com/relational-databases-arent-dinosaurs-theyre-sharks/).

this page has an approach for evaluating the boringness of technologies.

## bts

bts is the boring technology score. you calculate bts by multiplying the following factors:

* longevity (<5 years = 0, 5 years = 0.1, 6 years = 0.15, 10 years = 0.5, 20 years = 1.0)
* accidental complexity (including dependencies) (0.1 = extremly high, 0.5 = medium, 0.9 = extremely low)
* community (github stars)

## extremely boring technology stack

*extremely boring technology stack* is an opinionated technology stack that works
surprisingly large number of use cases. accidental complexity is minimized by [just using
postgres for everything](https://www.amazingcto.com/postgres-for-everything/), using 
multi-page app for almost everything, and when you can't, use 
[hypermedia-driven app](https://htmx.org/essays/hypermedia-driven-applications/) (HDA).

| technology | name | bts| replaces | comments |
| --- | --- | --- | --- | --- |
| backend | django | | fastapi, flask | |
| frontend | django | | REST + react/vue | for most views |
| frontend | django | | REST + react/vue | for admin  ui
| frontend | htmx/alpinejs | | REST + react/vue | for SPA uis
| database | postgres | | sqlite, mysql |
| background tasks | django-tasks | | celery | celery established, but too complex
| caching | django | | redis |
| caching | django-distill | | redis | for 'webscale' caching, use django-distill + s3 + cdn
| full-text search | postgres | | elastic |
| queue | postgres | | rabbitmq, kafka | postgres queues have ACID
| periodic running | superchronic | | cron | cron that runs in container
| multi-process | honcho | | systemd, k8s |
| dependencies | pip | | poetry, uv | uv looks promising, but so did poetry
| deployments | docker + paas | | k8s |
