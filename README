# Batcher

This is a small proof-of-concept for script for running (a large number) of
batch jobs, in parallel and resumable (in the event of a crash or intentional
abort).

It works for any kind of job where you can summarize what you need to do by (a)
writing a Perl function, and (b) feeding each iteration with one (text) line of
information.

Let's say that you have a million items in a database that you want to feed
into a search engine. You would then query your database for the IDs of the
items, write these IDs into (for example) a thousand files, with a thousand IDs
in each file, and then use `batcher` to process these files. – Since you have a
thousand files, you can then run up to a thousand parallel processes. If you
(for some reason) need to abort, just kill your Batcher processes, and when
your restart them they will pick up where they left off.
