Python module for the normalization of ternary generalized
pseudostandard words. Examples can be found in the Jupyter notebook
`Examples.ipynb`

### API:

### *class* `tgpc.Normalizer012`

Bases: `object`

Object for normalizing a ternary directive bi-sequences using the new
normalization algorithm.

`normalize(delta, theta)`

Ternary normalization algorithm.

Normalization function that returns the normalized directive bi-sequence
giving the same generalized pseudostandard word as (delta, theta).

<table>
<tbody>
<tr class="odd">
<td>Parameters:</td>
<td><ul>
<li><strong>delta</strong> (<em>str</em>) – The sequence delta of the directive bi-sequence. It should be composed of the letters ‘0’, ‘1’ and ‘2’.</li>
<li><strong>theta</strong> (<em>str</em>) – The sequence theta of the directive bi-sequence. It should be composed from the letters ‘R’, ‘0’, ‘1’ and ‘2’, where the last three stand for E_0, E_1 and E_2.</li>
</ul></td>
</tr>
<tr class="even">
<td>Returns:</td>
<td><p>Returns the tuple (new_delta, new_theta, notchanged) where (new_delta, new_theta) is the normalized bi-sequence of (delta, theta). The boolean notchanged is True if the bi-sequence (delta, theta) was already normalized, otherwise it is False.</p></td>
</tr>
</tbody>
</table>

Examples

    >>> n = Normalizer012()
    >>> n.normalize("0011", "00RR")
    ('0011', '00RR', True)

    >>> n.normalize("0102110", "02R0121")
    
 `print_all_factor_rules()`
Prints in a readable form all the factor normalization rules

-----------------------------------

### *class* `tgpc.NaiveNormalizer012`

Bases: `object`

Object for normalizing ternary directive bi-sequences using a naive
algorithm.

`normalize(delta, theta)`

Ternary naive normalization algorithm.

Naive normalization function that returns the normalized directive
bi-sequence giving the same generalized pseudostandard word as (delta,
theta). It creates the prefixes w\_i by generalized pseudopalindromic
closures a then checks if those are the only pseudopalindromic prefixes
in the word created by the directive bi-sequence.

<table>
<tbody>
<tr class="odd">
<td>Parameters:</td>
<td><ul>
<li><strong>delta</strong> (<em>str</em>) – The sequence delta of the directive bi-sequence. It should be composed of the letters ‘0’, ‘1’ and ‘2’.</li>
<li><strong>theta</strong> (<em>str</em>) – The sequence theta of the directive bi-sequence. It should be composed from the letters ‘R’, ‘0’, ‘1’ and ‘2’, where the last three stand for E_0, E_1 and E_2. Theta should be of the same length as delta.</li>
</ul></td>
</tr>
<tr class="even">
<td>Returns:</td>
<td><p>Returns the tuple (new_delta, new_theta, notchanged) where (new_delta, new_theta) is the normalized bi-sequence of (delta, theta). The boolean notchanged is True if the bi-sequence (delta, theta) was already normalized, otherwise it is False.</p></td>
</tr>
</tbody>
</table>

Examples

    >>> nn = NaiveNormalizer012()
    >>> nn.normalize("0011", "00RR")
    ('0011', '00RR', True)

    >>> nn.normalize("0102110", "02R0121")
    ('01021102', '02R01201', False)
    

-------------------------------------------------------------------
`tgpc.Ei(i)`
  The involutory antimorphism Ei.

<table>
<tbody>
<tr class="odd">
<td>Parameters:</td>
<td><strong>i</strong> – Either 0, 1, 2 or “0”, “1”, “2”</td>
</tr>
<tr class="even">
<td>Returns:</td>
<td>A tuple corresponding to the involutory antimorphism Ei.</td>
</tr>
</tbody>
</table>

Examples

    >>> Ei(0)
    ('0', '2', '1')
    >>> Ei(1)
    ('2', '1', '0')
    >>> Ei(2)
    ('1', '0', '2')
    
`tgpc.is_eipal(seq, i)`
Checks if a word is an Ei-palindrome.

<table>
<tbody>
<tr class="odd">
<td>Parameters:</td>
<td><ul>
<li><strong>seq</strong> (<em>string</em>) – The word checked composed of the letters “0”, “1” and “2”.</li>
<li><strong>i</strong> – Pseudopalindromic type, can be either 0, 1, 2, or “0”, “1”, “2”, standing for E_0, E_1 and E_2.</li>
</ul></td>
</tr>
<tr class="even">
<td>Returns:</td>
<td><p>True if the word is an Ei-palindrome, otherwise False.</p></td>
</tr>
</tbody>
</table>

Examples

    >>> is_eipal("012", 1)
    True
    >>> is_eipal("002", 1)
    False
    
`tgpc.is_pal(seq)`
Checks if a word is an R-palindrome.

<table>
<tbody>
<tr class="odd">
<td>Parameters:</td>
<td><strong>seq</strong> (<em>string</em>) – The word checked.</td>
</tr>
<tr class="even">
<td>Returns:</td>
<td>True if the word is an Ei-palindrome, otherwise False.</td>
</tr>
</tbody>
</table>

Examples

    >>> is_pal("012")
    False
    >>> is_pal("010")
    True
    
`tgpc.make_eipal_closure(seq, i)`
Makes an Ei-palindromic closure of a string.

<table>
<tbody>
<tr class="odd">
<td>Parameters:</td>
<td><ul>
<li><strong>seq</strong> (<em>string</em>) – A word composed of the letters “0”, “1” and “2”.</li>
<li><strong>i</strong> – Pseudopalindromic type, can be either 0, 1, 2, or “0”, “1”, “2”, standing for E_0, E_1 and E_2.</li>
</ul></td>
</tr>
<tr class="even">
<td>Returns:</td>
<td><p>The palindromic closure of the word.</p></td>
</tr>
</tbody>
</table>

Examples

    >>> make_eipal_closure("102", 0)
    '102'
    >>> make_eipal_closure("101", 1)
    '10121'

`tgpc.make_pal_closure(seq)`
Makes a palindromic closure of a string.

<table>
<tbody>
<tr class="odd">
<td>Parameters:</td>
<td><strong>seq</strong> (<em>string</em>) – A word.</td>
</tr>
<tr class="even">
<td>Returns:</td>
<td>The palindromic closure of the word.</td>
</tr>
</tbody>
</table>

Examples

    >>> make_pal_closure("101")
    '101'
    >>> make_pal_closure("102")
    '10201'
    
`tgpc.make_word012(delta, theta,*seed='')`
Makes a ternary GPS word from (delta, theta).

<table>
<tbody>
<tr class="odd">
<td>Parameters:</td>
<td><ul>
<li><strong>delta</strong> (<em>str</em>) – The sequence delta of the directive bi-sequence, composed of the letters ‘0’, ‘1’ and ‘2’.</li>
<li><strong>theta</strong> (<em>str</em>) – The sequence theta of the directive bi-sequence, composed from the letters ‘R’, ‘0’, ‘1’ and ‘2’, where the last three stand for E_0, E_1 and E_2. Must have the same length as delta.</li>
<li><strong>seed</strong> (<em>str</em>) – seed (initial w_0), optional.</li>
</ul></td>
</tr>
<tr class="even">
<td>Returns:</td>
<td><p>A string made by pseudopalindromic closure from (delta, theta).</p></td>
</tr>
</tbody>
</table>

Examples

    >>> make_word012("0011", "012R")
    '00221112200'

`tgpc.set_logging(logging level='ERROR')`
Sets the logging level of the module.

If the level is set to “ERROR”, the functions log only errors. If it is
set to “INFO” or “DEBUG”, the fuction prints more information about how
ternary words are being processed.

<table>
<tbody>
<tr class="odd">
<td>Parameters:</td>
<td><strong>level</strong> (<em>str</em>) – “ERROR” (default), “INFO” or “DEBUG”</td>
</tr>
</tbody>
</table>
