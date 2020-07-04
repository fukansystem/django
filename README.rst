Fork of django/django to cherry-pick patches for Fukan system.

Cherry-picks:

    | $ git cherry-pick 3cd3bebe8921e14b911b36b2a1cbceef8fb6294e

Documentation updates:

    | $ git cherry-pick ce5a70826c31b1e575b892edb8833f7559d91fc1
    | $ git cherry-pick e82ec9205d2c7afa2207fd5e62a597062013d9a2
    | $ git cherry-pick 0bdde9babe47f41f0d6ae6d52608e5e0f55da335
    | $ git cherry-pick e0f1aa10068fde9b62f551031defdc78affd2a35

To run affected tests:

    | $ docker run -it --rm -v $(pwd):/src \
    |     asia.gcr.io/fukansystem3/runtime /bin/ash
    | # cd /src/tests
    | # apk add --no-cache \
    |     build-base libffi-dev libmemcached-dev musl-dev python3-dev zlib-dev
    | # pip3 install -r requirements/py3.txt --user
    | # PYTHONPATH='/src' python3 ./runtests.py migrations.test_loader

To rebase on the upstream:

    | $ git remote add upstream https://github.com/django/django.git
    | $ git fetch upstream
    | $ git checkout stable/3.0.x
    | $ git rebase upstream/stable/3.0.x
    | $ git push -f origin stable/3.0.x
