renaming files
use rename 's/from/to/' *.extention

example:
>ls | grep .mp3
Lamb Of God - 11th Hour.mp3		Lame Of God - Vigil.mp3
Lamb Of God - Ruin.mp3			Lame Of God - The Faded Line.mp3

> rename 's/Lame Of God/Lamb Of God/' *.dat
>ls | grep .mp3
Lamb Of God - 11th Hour.mp3		Lamb Of God - Vigil.mp3
Lamb Of God - Ruin.mp3			Lamb Of God - The Faded Line.mp3
