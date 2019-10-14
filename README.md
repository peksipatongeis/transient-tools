# Transient Tools

I had the grand idea of running a self-updating remote development environment and ended up going with Container Linux (formerly CoreOS Linux).

As Container Linux doesn't come with a package manager I quickly realized that if I wanted to run any tools like `composer`, `node` or `docker-compose` I couldn't easily install them on the remote machine. So I ended creating scripts for each running them as [Transient Containers](https://adamcod.es/2017/05/22/docker-patterns-transient-container.html).

I have these scripts installed in `$HOME/.local/bin` and I have that directory added to `$PATH`.

As `docker run` won't automatically pull the latest image if the tag already exists locally you need to update those local images by pulling them manually. This can be the case if you are using major or minor releases (e.g. `node:10`) or the `latest` tag.