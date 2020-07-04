Fork of django/django to cherry-pick patches for Fukan system.

Cherry-picks:

    | $ git cherry-pick 29150d5da880ac1db15e47052330790cf1b802d2
    | $ git cherry-pick 32fbccab406b680bc0a0a8d39a9b95c3a08bbc5a
    | $ git cherry-pick 3cd3bebe8921e14b911b36b2a1cbceef8fb6294e

To run affected tests:

    | $ docker run -it --rm -v $(pwd):/src asia.gcr.io/fukansystem3/runtime /bin/bash
    | # cd /src/tests
    | # pip install -r requirements/py3.txt --user
    | # PYTHONPATH='/src' ./runtests.py migrations.test_loader

To rebase on the upstream:

    | $ git remote add upstream https://github.com/django/django.git
    | $ git fetch upstream
    | $ git checkout stable/3.0.x
    | $ git rebase upstream/stable/3.0.x
    | $ git push -f origin stable/3.0.x
