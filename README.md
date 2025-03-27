# rain.contribute

We love open source contributions, and will often even pay for them, but they
have to add value.

This is a repository of information explaining how to add value.

Most of the time, content has been added here due to some real world experience
where the instructions were not followed, and this experience was bad enough for
us to feel compelled to write about it.

In that context, we're unlikely to change our minds on the matter without at
least some deep conversation. We're also unlikely to entertain deep conversation
about any topic here with anyone who hasn't first shown an appreciation of why
things are the way they are, lest we fall to bikeshedding or worse.

## Target audience

This repository of information is aimed at those who want to provide technical
contributions and is targeted at a skilled audience.

You're expected to be able to read the contents of the repository, and navigate
git history, without us standing up some static site shell just to render the
`.md` files into equivalent `.html` files.

## Repo structure

The folder structure in this repository is intended to behave much like a simple
hierarchical navigation. Documents higher in the tree are more generally
applicable, while those further down are more specialized and may even override
or contradict more general advice, in more specific contexts represented by their
structural specificity.

For example:

```
code-style
  \__ rust
    \__ comments.md
  \__ sol
    \__ comments.md
  comments.md
```

This means that there is some generic advice on code comments in
`code-style/comments.md` that apply everywhere, unless/until some advice in
`code-style/rust/comments.md` or `code-style/sol/comments.md` contracts it. In
which case, you should use the more specific Rust advice when coding in Rust and
the Solidity advice when coding in Solidity.