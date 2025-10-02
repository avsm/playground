FROM mcr.microsoft.com/devcontainers/base:ubuntu-24.04

RUN apt-get update && apt-get -y install m4 build-essential autoconf opam

RUN opam init -a --disable-sandboxing --yes --bare && \
        opam update -a && \
        opam switch create 5.2.0+ox --yes \
        --repos "ox=git+https://github.com/oxcaml/opam-repository.git,default" && \
        eval $(opam env --switch 5.2.0+ox)

RUN opam install -y ocamlformat merlin ocaml-lsp-server odoc utop core parallel && opam clean -a
