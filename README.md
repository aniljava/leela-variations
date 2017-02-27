# leela-variations

Takes a SGF file as an input and creates different variations using Leela Go Engine and
outputs as another SGF file.

Leela's GTP interface provides the move sequences as well as variation sequences with win
probablity and other metadata. The script plays the existing game from SGF and adds moves
suggested by Leelas as alternative variations.


# Running
1. Download Leela Binary from https://sjeng.org/leela.html and extract binaries to project folder.
2. Edite leela-gtp (shell script to change binary name if it is not GPU)
2. Install dependencies `pip install gomill`
3. ./generator input.sgf output.sgf
4. Let the program run