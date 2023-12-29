//ctrl+shift+f
u_bookName = TEXTBEFORE(
    TEXTAFTER(CELL("filename", INDIRECT("A1")), "\[", -1),
    "]",
    -1
);

uo_bookName = LET(
    _cellFN, CELL("filename", INDIRECT("A1")),
    _sBracketsStart, FIND("[", _cellFN),
    _sBracketsEnd, FIND("]", _cellFN),
    MID(
        _cellFN,
        _sBracketsStart + 1,
        _sBracketsEnd - _sBracketsStart - 1
    )
);