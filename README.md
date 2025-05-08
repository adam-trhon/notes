Random tips, tricks and notes

Git
===
- Show list of dangling commits with short description:

      git fsck --lost-found | grep "^dangling commit" | sed "s/^dangling commit //g" | xargs git show -s --oneline

- To apply a patch, use this for more robust apply that allows conflict resolution:

      git apply --3way /path/to/patch

- To generate graph that optimizes tig with very large repositories (such as linux kernel):

      git commit-graph write --reachable --changed-paths

Yocto
===
- There is a [ROOT_HOME](https://docs.yoctoproject.org/ref-manual/variables.html#term-ROOT_HOME) variable that changes root home.
- An example for out-of-tree linux driver is in `poky/meta-skeleton/recipes-kernel/hello-mod/hello-mod_0.1.bb`.
- Overrides have [FOO:pn-myrecipe](https://docs.yoctoproject.org/ref-manual/variables.html#term-OVERRIDES) which can override `myrecipe` variable `FOO` from outside of the recipe (e.g. local.conf).
  - Beware the `pn-` prefix.
