# Warming up
## CI with C#

C# is a compiled language, so the first thing that a CI pipeline could do is to make sure
the commtited code compiles. This catches the most obvious errors in e.g. typing and syntax.
The compiler can also be configured to be strict when it comes to warnings, and e.g. always
treat them as errors.

The C# project / code base should contain high-priority unit tests that are run for each commit,
making sure the most core features are not affected by the changes. In addition, the CI pipeline
can contain nightly unit tests, that make sure that everything still works by the end of the day as
it did before.
Static code analysis can be incorporated to the CI pipeline to further enforce the style guidelines,
and to find issues related for example to returning `NaNs` or `Nulls`.

If one does not want to use Jenkins or GitHub actions for their pipeline, other alternatives
include Azure DevOps and TeamCity. Whether a smallish team of 6 uses self-hosted CI pipeline or a cloud-one
should be dependent on their resources. Cloud would have smaller maintenance overhead, but incurs running costs.
Having local CI system could be cheaper, especially with pre-existing infrastructure and infra-team outside the 
developer team. However, if this is not the case, local solution might necessitate one developer to be designated
as build-system nanny, which might impact the team output.
