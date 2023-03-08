# Logism Project #1

### Group: Bee Ball, Nia Sparacino, Joshua Ramon-Cruz, Patrick Watkins

This project utilizes Logisim and Logisim Evolution to create a simple 7-segment display driver with two logic circuits to handle decimal 0-9 and hex 0-F display logic. 

The circuit design was originally created in Logisim Evolution, then adapted to Logisim code for compatibility.

---

## Truth Table

| input | w | x | y | z | output  | a | b | c | d | e | f | g | decimal display | hex display |
|-------|---|---|---|---|---------|---|---|---|---|---|---|---|-----------------|-------------|
| 0000  | 0 | 0 | 0 | 0 | 1111110 | 1 | 1 | 1 | 1 | 1 | 1 | 0 | 0               | 0           |
| 0001  | 0 | 0 | 0 | 1 | 0110000 | 0 | 1 | 1 | 0 | 0 | 0 | 0 | 1               | 1           |
| 0010  | 0 | 0 | 1 | 0 | 1101101 | 1 | 1 | 0 | 1 | 1 | 0 | 1 | 2               | 2           |
| 0011  | 0 | 0 | 1 | 1 | 1111001 | 1 | 1 | 1 | 1 | 0 | 0 | 1 | 3               | 3           |
| 0100  | 0 | 1 | 0 | 0 | 0110011 | 0 | 1 | 1 | 0 | 0 | 1 | 1 | 4               | 4           |
| 0101  | 0 | 1 | 0 | 1 | 1011011 | 1 | 0 | 1 | 1 | 0 | 1 | 1 | 5               | 5           |
| 0110  | 0 | 1 | 1 | 0 | 1011111 | 1 | 0 | 1 | 1 | 1 | 1 | 1 | 6               | 6           |
| 0111  | 0 | 1 | 1 | 1 | 1110000 | 1 | 1 | 1 | 0 | 0 | 0 | 0 | 7               | 7           |
| 1000  | 1 | 0 | 0 | 0 | 1111111 | 1 | 1 | 1 | 1 | 1 | 1 | 1 | 8               | 8           |
| 1001  | 1 | 0 | 0 | 1 | 1110011 | 1 | 1 | 1 | 0 | 0 | 1 | 1 | 9               | 9           |
| 1010  | 1 | 0 | 1 | 0 | 1110111 | 1 | 1 | 1 | 0 | 1 | 1 | 1 | X               | W           |
| 1011  | 1 | 0 | 1 | 1 | 0011111 | 0 | 0 | 1 | 1 | 1 | 1 | 1 | X               | b           |
| 1100  | 1 | 1 | 0 | 0 | 1001110 | 1 | 0 | 0 | 1 | 1 | 1 | 0 | X               | C           |
| 1101  | 1 | 1 | 0 | 1 | 0111101 | 0 | 1 | 1 | 1 | 1 | 0 | 1 | X               | d           |
| 1110  | 1 | 1 | 1 | 0 | 1001111 | 1 | 0 | 0 | 1 | 1 | 1 | 1 | X               | E           |
| 1111  | 1 | 1 | 1 | 1 | 1000111 | 1 | 0 | 0 | 1 | 1 | 1 | 1 | X               | F           |

---

## Boolean Wlgebra

### Hex Display Logic

The boolean algebra for the hex display is unsimplified SOP form and the logic gates are also unsimplified, with each pin's logic being their respective combination of inputs running into and gates whose output runs into or gates for the final pin's output

- a = X'Z' + W'Y + XY + WZ' + W'XZ + WX'Y'
- b = W'X' + X'Z' + W'Y'Z' + W'YZ + WY'Z
- c = W'Y' + W'Z + W'X + Y'Z + WX'
- d = WY' + W'X'Z' + X'YZ + XY'Z + XYZ'
- e = WX + WY + X'Z' + YZ'
- f = WX' + WY + XZ' Y'Z' + W'XY'

### Decimal Display Logic (included even though the logic was already done in the hex display)

The boolean algebra for the decimal display is in a hand-simplified form, done out of boredom and curiosity and included as a bonus. The algebra was "simplified" down to use as little logic gates as possible, but is definitely imperfect and really doesn't make a whole ton of sense.

- a = W + XZ + X'Z' + Y
- b = X' + Y'Z' + YZ
- c = X + Y' + Z
- d = Z'Y'Z'+ W'(Y ⊕ XZ)
- e = Z'(X' + Y)
- f = W + XY' + XZ' + Y'Z'
- g = W + XY' + X'Y + YZ'

### Quirks
For some reason my hacky fix for the hex counter in Logisim Evolution made it update on the falling edge of the clock. No difference in the logic's functionality, just some weird quirk in my imperfect conversion. 

---

- Bee: Decimal Logic Solving + Simplifying, README + Github Creation, Logisim Evolution Implementation, Logisim Conversion, General Collaboration + Support
- Nia: Hex Logic Solving + Conversion to SOP Form, General Collaboration + Support
- Joshua: Group Communication, General Collaboration + Support
- Patrick Watkins: General Collaboration + Support

