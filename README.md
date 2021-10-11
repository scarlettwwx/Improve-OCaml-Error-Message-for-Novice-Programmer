## Installing LearnOCaml locally

Locally install LearnOCaml using the following:

```bash
git clone https://github.com/teaching-the-art-of-fp/learn-ocaml.git
cd learn-ocaml
git checkout teaching-fp
opam switch create . --deps-only --locked
opam install opam-installer
eval $(opam env)
make && make opaminstall
```

On Ubuntu 20.04, a `libev` dependency may not be met.
Use `sudo apt-get install libev-dev` to install it, then re-run `opam install . --deps-only --locked`.

## Organizing assignment submissions

Organize assignment submissions from myCourses by student ID using the following:

```bash
python3 ./organize_submissions.py \
--class-list="./COMP 302 Students.csv" \
--assignments-directory="./A1" \
--output-directory="./A1 - Organized" \
--comment-submission-file-name
```

Note that if two students share the same full name, then their submissions need to be organized manually.

## Grade assignments with LearnOCaml

Grade organized submissions with a local installation of LearnOCaml using the following:

```bash
python3 ./generate_offline_reports.py \
--class-list="./COMP 302 Students.csv" \
--exercise="./exercises/learn-ocaml-repo-fall2021/exercises/hw3" \
--submissions="./A3 - Organized" \
--output="./A3 - Grades" \
--timeout=60 --tests=5
```
