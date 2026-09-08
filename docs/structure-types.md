# Adding New Structure Types

To print the location of the burn reflections file (in the conda environment
with "polylaue" active), run the following command:

```bash
python -c "from polylaue.model.core import burn_reflections; print(burn_reflections.__file__)"
```

You can then edit that file. At the top of the file, you will see a
BASIC_STRUCTURE_TYPES list and an ADVANCED_STRUCTURE_TYPES list. You can add
the new structure type to one of those two lists. If it's a structure type
that several users would use, then you can add it to the BASIC list. If it's
a structure type that not many people will use, then you can add it to the
ADVANCED list (then it would only show up if the user checked to "Include
Advanced Structure Types"). Then in the `burn()` code, add the logic for
handling the structure type (it will be called `structure_type` in the
code).

When you restart PolyLaue, it will include the changes.

After updating of PolyLaue to the latest version locally defined structure
types will be vanished. Saving burn reflections file in a separate location
before updating and overwriting the file in its normal location after
updating, will solve the problem.
