# leela-variations

Generates variations for each move in given SGF file. The variations are the top branches
Leela engine visited before picking the best one among them. Leela suggests the first top
move and a expected list of move beyond that. It is not confirmed as further evaluation is
done in next move but provides a close picture of moves to come.

# Running the program (Tested in Ubuntu/Linux)
1. Install dependencies : `# pip install gomill`
2. If new version of Leela is available (9.0 is included in `leela-binary` folder , download the binary and replace contents of `leela-binary` folder. Make edit main script `leela-variation` to change the name of binary file.
3. Execute scrupt as `./leela-variations <source.sgf> <destination.sgf>

Takes a while to complete the playout producting destination.sgf with variations alogn the way.

# Todo
- Extend variation using actual extended play in branches as well
- Fix script to support Windows, Linux 