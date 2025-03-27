# Evidence in software development

Evidence based software development and and Quality Assurance are closely related
and often indistinguishable.

All but the most trivial codebases have more combinatorial complexities implied
in their structures than there are atoms in the universe.

Consider Dijkstra's classic example of multiplying two numbers. We cannot
directly test that `a * b = c` gives us the correct answer for all `a` and `b`
for even a humble `u32` let alone the `uint256` beasts in Solidity.

"Proof by exhaustion" is therefore not possible, so all we can do is try to
explore as many representative regions of the solution space as we can, in the
most efficient way possible.

An example is the fuzzer in Foundry for testing Solidity code. Faced with
basically every value having ~2^256 possible values, they generate values
over log rather than linear space (e.g. bits as coin flips in the binary), with
some additional logic to pay special attention to known troublemakers such as
`0` and `type(uint256).max`.

## Happy path thinking is self sabotage

When we write code, we think about what we want the code to do.

The process is something like

- The code does not exist
- Code exists but does not compile
- Code compiles, but we've never seen it do what we want
- We've seen the code do what we want once
- We've seen the code do what we want several times
- We can't produce any scenarios where the code doesn't do what we want

Happy path thinking skips the last and very crucial step. The step where we
actually create reproducible scenarios (aka "tests") and exhaust ourselves and
our creativity in producing more.

Common culprits include

- Failing to test error/edge cases
- Failing to test different families of numerics
    - `0`, `1`, plurals, negatives, infinites, NaNs, floats, etc.
- Failing to test corrupt data, e.g. invalid utf-8 bytes in strings, etc.

One of the main benefits of moving from example based testing to generative/fuzz
testing is that deviation from the happy path is the default, making it much more
difficult to get stuck in a false sense of security.
