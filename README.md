# Pybiomes

An **unfinished** port of [Cubiomes](https://www.github.com/Cubitect/cubiomes), by [Cubitect]((https://www.github.com/Cubitect)) et. al., to Python 3.10+.

This library is not intended for "formal" seedfinding: a program written in C, CUDA, or even as a [Cubiomes Viewer](https://www.github.com/Cubitect/cubiomes-viewer) session file will run incomparably faster than the same program written in Python. However, this library does have use as
- an introduction for anyone interested in seedfinding but who isn't familiar with other languages, and as
- an exercise for myself in writing a full type-safe Python package. (This project also allows me to refactor certain Cubiomes constructs that I personally wish had been implemented differently.)

It should be emphasized that this is not an exact clone of the library: there are multiple syntactical and semantical differences between this library and the original library, and one should also not expect this library to necessarily be regularly updated whenever Cubiomes is.

<!-- ## Installing
1. In your terminal of choice ([Bash](https://en.wikipedia.org/wiki/Bash_(Unix_shell)), [cmd](https://en.wikipedia.org/wiki/Cmd.exe), [PowerShell](https://learn.microsoft.com/en-us/powershell/scripting/overview), etc.), type
```bash
pip install pybiomes
```
2. Then in one's Python's program, type
```python
import pybiomes
```
to import the library and its features.

## Example Programs
```python
import pybiomes

generator = pybiomes.Generator(Version.V1_20)
coordinateToCheck = pybiomes.Coordinate(0, 63, 0)
for seed in range(2**64):
  generator.apply(seed)
  biome = generator.getBiomeAt(coordinateToCheck)
  if biome != pybiomes.Biome.MUSHROOM_FIELDS: continue
  print(f"Seed {seed} has a mushroom fields biome at {coordinate}.")
  break
```

```python
import pybiomes

SEED = 123

generator = pybiomes.Generator(Version.V1_20, SEED, largeBiomes=True)
coordRange = pybiomes.Range((-60, 60, -60), (60, 60, 60))
biomes = generator.generateBiomes(coordRange)
...
```

```python
import pybiomes

generator = pybiomes.Generator(Version.V1_20)
structureSearcher = pybiomes.Structures(pybiomes.Structures.ID.Outpost, generator=generator)
for structureSeed in range(2**48):
  blockCoordinate = structureSearcher.getTheoreticalCoordinate((0, 0), structureSeed)
  if blockCoordinate is None or blockCoordinate != Coordinate(0, 0): continue
  for topBits in range(2**16):
    seed = (topBits << 48) + structureSeed
    structureSearcher.apply(seed)
    if structureSearcher.isViableCoordinate(blockCoordinate):
      print(f"Seed {seed} has a pillager outpost at {blockCoordinate}.")
      break
```

```python
import pybiomes

SEED = 3055141959546
STRONGHOLDS_TO_GENERATE = 12

strongholdIterator = pybiomes.StrongholdIterator(Version.V1_20, SEED)
for i, strongholdPos in enumerate(strongholdIterator):
  if i >= STRONGHOLDS_TO_GENERATE: break
  if strongholdPos is not None: print(f"Seed {SEED} has stronghold #{i + 1} approximately at {strongholdPos}.")

generator = pybiomes.Generator(Version.V1_20, SEED)
print(f"Seed {SEED} has its spawnpoint approximately at {generator.getSpawnpoint()}.")
``` -->