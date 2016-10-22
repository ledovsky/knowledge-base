# Mapping в Vim

Копия ответа StackOverflow. Источник: http://stackoverflow.com/questions/3776117/what-is-the-difference-between-the-remap-noremap-nnoremap-and-vnoremap-mapping


remap is an option that makes mappings work recursively. By default it is on and I'd recommend you leave it that way. The rest are mapping commands, described below:

:map and :noremap are recursive and non-recursive versions of the various mapping commands. What that means is that if you do:

    :map j gg
    :map Q j
    :noremap W j

j will be mapped to gg. Q will also be mapped to gg, because j will be expanded for the recursive mapping. W will be mapped to j (and not to gg) because j will not be expanded for the non-recursive mapping.

Now remember that Vim is a modal editor. It has a normal mode, visual mode and other modes.

For each of these sets of mappings, there is a mapping that works in normal, visual, select and operator modes (:map and :noremap), one that works in normal mode (:nmap and :nnoremap), one in visual mode (:vmap and :vnoremap) and so on.

For more guidance on this, see:

    :help :map
    :help :noremap
    :help recursive_mapping
    :help :map-modes


