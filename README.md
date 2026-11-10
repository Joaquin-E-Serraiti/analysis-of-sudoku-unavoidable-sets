# Analysis of Minimal Unavoidable Sets
![](/images/first_image.webp)

## INTRODUCTION
In this document I attempt to analyze and classify the structure of some (not all) minimal unavoidable sets in Sudoku.

The names and terminology I use might not be the best or might conflict with other Sudoku terms. If you know of better alternatives, let me know.

If you notice any mistakes, incorrect statements, confusing or incomplete explanations, or think of some information that could be added to this document, feel welcome to send me corrections and suggestions.

I’m not an expert in Sudoku. I’m just sharing information and ideas I’ve been thinking about and find interesting.

## SOME DEFINITIONS
### What is an unavoidable set?
An unavoidable set is a set of cells in a solved Sudoku grid that, if we remove its digits, produces an incomplete grid with more than one possible solution.

### What is a minimal unavoidable set?
Some unavoidable sets contain other unavoidable sets, meaning that a subset of the cells of the unavoidable set form another unavoidable set. A minimal unavoidable set is a set that does not contain other unavoidable sets.

### Examples
![](/images/ua_example.webp)

<sup>
  
- 000000000000430000000000000000120000000340000000000000000210000000000000000000000
  
- 328951746516437289794682351485129637967348512132576894653214978271895463849763125

</sup>

Above is an example of an unavoidable set in a complete grid. When we remove the digits from the cells of the unavoidable set, the resulting incomplete grid has more than one solution (you can try finding all the solutions).

However, that unavoidable set contains two minimal unavoidable sets.

![](/images/mua_example.webp)

By removing only the digits from the cells of one of the two minimal unavoidable sets, we also get an incomplete grid with more than one solution.

It is important to note that, as long as any cell in a minimal unavoidable set isn’t empty, and all the cells in the grid that do not belong to the set are filled, the digits in all of the other cells in the set can be deduced. In other words, filling any cell in the set eliminates the ambiguity (multiple solutions) produced by leaving all cells of the set empty.

## SOME BASIC TYPES OF MINIMAL UNAVOIDABLE SETS

### The AB-BA-AB type

![](/images/ab-ba-ab_example.webp)

<sup>
  
- 010020000020000010000010020000000000000000000000000000000000000000000000000000000

- 719823456325649718486715923698371542154982637237456891961538274542167389873294165
</sup>

Characteristics:
- Only has two digits.
- Occupies at least all three boxes in a band or stack.

### The ABC-BCA type

![](/images/abc-bca_example.webp)

<sup>
  
- 000000000000000000000000000000000000000000000000000000001000200002000300003000100
</sup>

Characteristics:
- Occupies at least two boxes in a band or stack.

### The chain type

![](/images/chain_type_example_1.webp)
![](/images/chain_type_example_2.webp)

<sup>

- 000000000000000000000000000000000000010020000020010000000000000000000000000000000

- 000000000000000000000000806000000000000000605000000000000000508000000000000000000
  
- 205698107000000000907152806000000000000000000000000000000000000000000000000000000

- 000000000000000000000000000000000000000000000000000000196243578372589461000000000

- 245698137861437952937152846589376214713924685624815793196243578372589461458761329
  
</sup>

Characteristics:
- Has between 2 and 9 digits.
- Occupies at least two boxes in a band or stack.


## THE CONNECTIVITY STRUCTURE

The previous images of minimal unavoidable sets show sets that occupy only one band or stack. However, these types of sets can occupy many bands or stacks.

Below is an example of a minimal unavoidable set of the chain type with two digits, occupying many bands and stacks, and with a simple connectivity structure.

![](/images/connectivity_structure_example.webp)

<sup>

- 010020000200010000000000000000000000120000000000000000000000000000000000000000000

- 716923584283514796549687321864375912127498653395162478972836145438751269651249837
  
</sup>

This set occupies boxes 1, 2 and 4. The parts in box 2 and 4 are connected through the 2 cells in box 1. I define those cells in box 1 as the “connector”.

When a minimal unavoidable set has no connectors, I refer to it as a set with no connectivity structure.

### Connectors

A connector serves as a link between two parts of an unavoidable set that are in different bands and/or stacks. You can think of the previous example as 2 minimal unavoidable sets of the chain type, one in the first band and one in the first stack, and box 1 had the connector, merging both sets into one.

A connector is formed by 2 cells in a box that are in different columns and rows. If 2 cells belong to the same column or row within a box, they don’t form a connector.

### Examples of different connectivity structures

These are examples of grids with AB-BA-AB minimal unavoidable sets with different connectivity structures:

![](/images/ab-ba-ab_connectivity_example_1.webp)

<sup>

- 000200010010000020020001000000000000000012000000000000000000000000120000000000000

- 357298416914673825628451793246985137579312684183764952831547269465129378792836541
  
</sup>

![](/images/ab-ba-ab_connectivity_example_2.webp)

<sup>

- 000000000012000000000000120000000000201000000000000012100020000000010200020000001

- 975162438812943657346785129687231594231594786594876312159427863768319245423658971
  
</sup>

![](/images/ab-ba-ab_connectivity_example_3.webp)

<sup>

- 002000001100020000000001200001000020000200100020010000000002010200100000010000002

- 942735681158629437673481295731864529865297143429513768586372914294158376317946852
  
</sup>

These are examples of minimal unavoidable sets of the chain type, with different connectivity structures:

![](/images/chain_connectivity_example_1.webp)

<sup>

- 000000000000102000000000000010200030000000000020003010000000000000301000000000000

- 594638721783142659261795348615289437437516982829473516148957263956321874372864195
  
</sup>

![](/images/chain_connectivity_example_2.webp)

<sup>

- 000000000320000054000000000000000000014025003205031040000000000130000000000000035

- 596417382321986754487253196863794521914825673275631849652348917139572468748169235
  
</sup>

![](/images/chain_connectivity_example_3.webp)

<sup>

- 010000200000000000020000001100030002000000000003020100001304020000000000300201040

- 716849253435162798829573461164735982287916534953428176671394825542687319398251647
  
</sup>

Lastly, these are examples of grids with ABC-BCA minimal unavoidable sets with different connectivity structures:

![](/images/abc-bca_connectivity_example_1.webp)

<sup>

- 000000000000000000000000000000020001000030002000100003000200010000300020000010030

- 164972358259683174387451269643825791915734682728196543836247915591368427472519836
  
</sup>

![](/images/abc-bca_connectivity_example_2.webp)

<sup>

- 010020000020030000030001000000002010000003020000010003000200001000300002000100030

- 514829367729536184836471259378952416691743528245618973453287691167395842982164735
  
</sup>

![](/images/abc-bca_connectivity_example_3.webp)

<sup>

- 010000020020000030300000001000000000000000000000000000100000002200000003030000010

- 815739426724615938369824751943176285671582394582493167197358642256941873438267519
  
</sup>

I find the ABC-BCA type to be more complex than the other two types of sets. I still don't completely understand all the ways it can have connectivity structures, and I'm not sure that the framework I defined is enough to understand it.

Also, I believe that, because the ABC-BCA type has three cells in each box, it can form up to three connectors per box, because a connector is formed by 2 cells and there are 3 ways of selecting 2 out of 3 cells. This might allow for weird connectivity structures.

### Some inferences

Because of how the distribution of digits works in solved grids, you can choose any pair of digits, and observe that they form minimal unavoidable sets of the AB-BA-AB type and/or the chain type, with different connectivity structures.

![](/images/ab-ba-ab_and_chain_type_partition.webp)

The set of 18 cells containing any two selected digits (which is an unavoidable set) can be partitioned into one or more minimal unavoidable sets of the AB-BA-AB type and/or the chain type.

Therefore, for each pair of digits, you can find at least one minimal unavoidable set of the AB-BA-AB or chain type in any grid. And because there are 36 different pairs of digits, any grid has at least 36 distinct minimal unavoidable sets of the AB-BA-AB and/or chain types.

Also, any selected pair of rows or columns in the same band or stack is an unavoidable set. That unavoidable set can be partitioned into one or more minimal unavoidable sets of the chain type only. This is also guaranteed by how the distribution of digits in solved grids work.

![](/images/)

Therefore, because each band and stack has 3 ways of selecting 2 out of its 3 rows or columns, and there are 3 bands and 3 stacks (6 in total), there are at least 18 (3 multiplied by 6) minimal unavoidable sets of the chain type in any grid.








