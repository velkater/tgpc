
<!DOCTYPE html PUBLIC "-//W3C//DTD XHTML 1.0 Transitional//EN"
  "http://www.w3.org/TR/xhtml1/DTD/xhtml1-transitional.dtd">         
<div class="section" id="module-tgpc">
<span id="tgpc-module"></span><h1>tgpc module<a class="headerlink" href="#module-tgpc" title="Permalink to this headline"></a></h1>
Python module for the normalization of ternary generalized pseudostandard words.    
Examples can be found in the Jupyter notebook `Examples.ipynb` 
  
</br>
<h3> API:</h3>
<dl class="function">
<dt id="tgpc.Ei">
<code class="descclassname">tgpc.</code><code class="descname">Ei</code><span class="sig-paren">(</span><em>i</em><span class="sig-paren">)</span><a class="headerlink" href="#tgpc.Ei" title="Permalink to this definition"></a></dt>
<dd><p>The involutory antimorphism Ei.</p>
<table class="docutils field-list" frame="void" rules="none">
<col class="field-name" />
<col class="field-body" />
<tbody valign="top">
<tr class="field-odd field"><th class="field-name">Parameters:</th><td class="field-body"><strong>i</strong> – Either 0, 1, 2 or “0”, “1”, “2”</td>
</tr>
<tr class="field-even field"><th class="field-name">Returns:</th><td class="field-body">A tuple corresponding to the involutory antimorphism Ei.</td>
</tr>
</tbody>
</table>
<p class="rubric">Examples</p>
<div class="highlight-default notranslate"><div class="highlight"><pre><span></span><span class="gp">&gt;&gt;&gt; </span><span class="n">Ei</span><span class="p">(</span><span class="mi">0</span><span class="p">)</span>
<span class="go">(&#39;0&#39;, &#39;2&#39;, &#39;1&#39;)</span>
<span class="gp">&gt;&gt;&gt; </span><span class="n">Ei</span><span class="p">(</span><span class="mi">1</span><span class="p">)</span>
<span class="go">(&#39;2&#39;, &#39;1&#39;, &#39;0&#39;)</span>
<span class="gp">&gt;&gt;&gt; </span><span class="n">Ei</span><span class="p">(</span><span class="mi">2</span><span class="p">)</span>
<span class="go">(&#39;1&#39;, &#39;0&#39;, &#39;2&#39;)</span>
</pre></div>
</div>
</dd></dl>

<dl class="class">
<dt id="tgpc.NaiveNormalizer012">
<em class="property">class </em><code class="descclassname">tgpc.</code><code class="descname">NaiveNormalizer012</code><a class="headerlink" href="#tgpc.NaiveNormalizer012" title="Permalink to this definition"></a></dt>
<dd><p>Bases: <code class="xref py py-class docutils literal notranslate"><span class="pre">object</span></code></p>
<p>Object for normalizing ternary directive bi-sequences using
a naive algorithm.</p>
<dl class="method">
<dt id="tgpc.NaiveNormalizer012.normalize">
<code class="descname">normalize</code><span class="sig-paren">(</span><em>delta</em>, <em>theta</em><span class="sig-paren">)</span><a class="headerlink" href="#tgpc.NaiveNormalizer012.normalize" title="Permalink to this definition"></a></dt>
<dd><p>Ternary naive normalization algorithm.</p>
<p>Naive normalization function that returns the normalized
directive bi-sequence giving the same generalized pseudostandard
word as (delta, theta). It creates the prefixes w_i by generalized
pseudopalindromic closures a then checks if those are the only
pseudopalindromic prefixes in the word created by the directive bi-sequence.</p>
<table class="docutils field-list" frame="void" rules="none">
<col class="field-name" />
<col class="field-body" />
<tbody valign="top">
<tr class="field-odd field"><th class="field-name">Parameters:</th><td class="field-body"><ul class="first simple">
<li><strong>delta</strong> (<em>str</em>) – The sequence delta of the directive bi-sequence.
It should be composed of the letters ‘0’, ‘1’ and ‘2’.</li>
<li><strong>theta</strong> (<em>str</em>) – The sequence theta of the directive bi-sequence.
It should be composed from the letters ‘R’, ‘0’, ‘1’ and
‘2’, where the last three stand for E_0, E_1 and E_2. Theta
should be of the same length as delta.</li>
</ul>
</td>
</tr>
<tr class="field-even field"><th class="field-name">Returns:</th><td class="field-body"><p class="first last">Returns the tuple <cite>(new_delta, new_theta, notchanged)</cite> where (new_delta, new_theta)
is the normalized bi-sequence of (delta, theta). The boolean <cite>notchanged</cite> is True
if the bi-sequence (delta, theta) was already normalized, otherwise it is False.</p>
</td>
</tr>
</tbody>
</table>
<p class="rubric">Examples</p>
<div class="highlight-default notranslate"><div class="highlight"><pre><span></span><span class="gp">&gt;&gt;&gt; </span><span class="n">nn</span> <span class="o">=</span> <span class="n">NaiveNormalizer012</span><span class="p">()</span>
<span class="gp">&gt;&gt;&gt; </span><span class="n">nn</span><span class="o">.</span><span class="n">normalize</span><span class="p">(</span><span class="s2">&quot;0011&quot;</span><span class="p">,</span> <span class="s2">&quot;00RR&quot;</span><span class="p">)</span>
<span class="go">(&#39;0011&#39;, &#39;00RR&#39;, True)</span>
</pre></div>
</div>
<div class="highlight-default notranslate"><div class="highlight"><pre><span></span><span class="gp">&gt;&gt;&gt; </span><span class="n">nn</span><span class="o">.</span><span class="n">normalize</span><span class="p">(</span><span class="s2">&quot;0102110&quot;</span><span class="p">,</span> <span class="s2">&quot;02R0121&quot;</span><span class="p">)</span>
<span class="go">(&#39;01021102&#39;, &#39;02R01201&#39;, False)</span>
</pre></div>
</div>
</dd></dl>

</dd></dl>

<dl class="class">
<dt id="tgpc.Normalizer012">
<em class="property">class </em><code class="descclassname">tgpc.</code><code class="descname">Normalizer012</code><a class="headerlink" href="#tgpc.Normalizer012" title="Permalink to this definition"></a></dt>
<dd><p>Bases: <code class="xref py py-class docutils literal notranslate"><span class="pre">object</span></code></p>
<p>Object for normalizing a ternary directive bi-sequences
using the new normalization algorithm.</p>
<dl class="method">
<dt id="tgpc.Normalizer012.normalize">
<code class="descname">normalize</code><span class="sig-paren">(</span><em>delta</em>, <em>theta</em><span class="sig-paren">)</span><a class="headerlink" href="#tgpc.Normalizer012.normalize" title="Permalink to this definition"></a></dt>
<dd><p>Ternary normalization algorithm.</p>
<p>Normalization function that returns the normalized directive
bi-sequence giving the same generalized pseudostandard
word as (delta, theta).</p>
<table class="docutils field-list" frame="void" rules="none">
<col class="field-name" />
<col class="field-body" />
<tbody valign="top">
<tr class="field-odd field"><th class="field-name">Parameters:</th><td class="field-body"><ul class="first simple">
<li><strong>delta</strong> (<em>str</em>) – The sequence delta of the directive bi-sequence.
It should be composed of the letters ‘0’, ‘1’ and ‘2’.</li>
<li><strong>theta</strong> (<em>str</em>) – The sequence theta of the directive bi-sequence.
It should be composed from the letters ‘R’, ‘0’, ‘1’ and
‘2’, where the last three stand for E_0, E_1 and E_2.</li>
</ul>
</td>
</tr>
<tr class="field-even field"><th class="field-name">Returns:</th><td class="field-body"><p class="first last">Returns the tuple <cite>(new_delta, new_theta, notchanged)</cite> where
(new_delta, new_theta) is the normalized bi-sequence of (delta, theta).
The boolean <cite>notchanged</cite> is True if the bi-sequence (delta, theta)
was already normalized, otherwise it is False.</p>
</td>
</tr>
</tbody>
</table>
<p class="rubric">Examples</p>
<div class="highlight-default notranslate"><div class="highlight"><pre><span></span><span class="gp">&gt;&gt;&gt; </span><span class="n">n</span> <span class="o">=</span> <span class="n">Normalizer012</span><span class="p">()</span>
<span class="gp">&gt;&gt;&gt; </span><span class="n">n</span><span class="o">.</span><span class="n">normalize</span><span class="p">(</span><span class="s2">&quot;0011&quot;</span><span class="p">,</span> <span class="s2">&quot;00RR&quot;</span><span class="p">)</span>
<span class="go">(&#39;0011&#39;, &#39;00RR&#39;, True)</span>
</pre></div>
</div>
<div class="highlight-default notranslate"><div class="highlight"><pre><span></span><span class="gp">&gt;&gt;&gt; </span><span class="n">n</span><span class="o">.</span><span class="n">normalize</span><span class="p">(</span><span class="s2">&quot;0102110&quot;</span><span class="p">,</span> <span class="s2">&quot;02R0121&quot;</span><span class="p">)</span>
<span class="go">(&#39;01021102&#39;, &#39;02R01201&#39;, False)</span>
</pre></div>
</div>
</dd></dl>

<dl class="method">
<dt id="tgpc.Normalizer012.print_all_factor_rules">
<code class="descname">print_all_factor_rules</code><span class="sig-paren">(</span><span class="sig-paren">)</span><a class="headerlink" href="#tgpc.Normalizer012.print_all_factor_rules" title="Permalink to this definition"></a></dt>
<dd><p>Prints in a readable form all the factor normalization rules</p>
</dd></dl>

</dd></dl>

<dl class="function">
<dt id="tgpc.is_eipal">
<code class="descclassname">tgpc.</code><code class="descname">is_eipal</code><span class="sig-paren">(</span><em>seq</em>, <em>i</em><span class="sig-paren">)</span><a class="headerlink" href="#tgpc.is_eipal" title="Permalink to this definition"></a></dt>
<dd><p>Checks if a word is an Ei-palindrome.</p>
<table class="docutils field-list" frame="void" rules="none">
<col class="field-name" />
<col class="field-body" />
<tbody valign="top">
<tr class="field-odd field"><th class="field-name">Parameters:</th><td class="field-body"><ul class="first simple">
<li><strong>seq</strong> (<em>string</em>) – The word checked composed
of the letters “0”, “1” and “2”.</li>
<li><strong>i</strong> – Pseudopalindromic type, can be either 0, 1, 2, or
“0”, “1”, “2”, standing for E_0, E_1 and E_2.</li>
</ul>
</td>
</tr>
<tr class="field-even field"><th class="field-name">Returns:</th><td class="field-body"><p class="first last">True if the word is an Ei-palindrome, otherwise False.</p>
</td>
</tr>
</tbody>
</table>
<p class="rubric">Examples</p>
<div class="highlight-default notranslate"><div class="highlight"><pre><span></span><span class="gp">&gt;&gt;&gt; </span><span class="n">is_eipal</span><span class="p">(</span><span class="s2">&quot;012&quot;</span><span class="p">,</span> <span class="mi">1</span><span class="p">)</span>
<span class="go">True</span>
<span class="gp">&gt;&gt;&gt; </span><span class="n">is_eipal</span><span class="p">(</span><span class="s2">&quot;002&quot;</span><span class="p">,</span> <span class="mi">1</span><span class="p">)</span>
<span class="go">False</span>
</pre></div>
</div>
</dd></dl>

<dl class="function">
<dt id="tgpc.is_pal">
<code class="descclassname">tgpc.</code><code class="descname">is_pal</code><span class="sig-paren">(</span><em>seq</em><span class="sig-paren">)</span><a class="headerlink" href="#tgpc.is_pal" title="Permalink to this definition"></a></dt>
<dd><p>Checks if a word is an R-palindrome.</p>
<table class="docutils field-list" frame="void" rules="none">
<col class="field-name" />
<col class="field-body" />
<tbody valign="top">
<tr class="field-odd field"><th class="field-name">Parameters:</th><td class="field-body"><strong>seq</strong> (<em>string</em>) – The word checked.</td>
</tr>
<tr class="field-even field"><th class="field-name">Returns:</th><td class="field-body">True if the word is an Ei-palindrome, otherwise False.</td>
</tr>
</tbody>
</table>
<p class="rubric">Examples</p>
<div class="highlight-default notranslate"><div class="highlight"><pre><span></span><span class="gp">&gt;&gt;&gt; </span><span class="n">is_pal</span><span class="p">(</span><span class="s2">&quot;012&quot;</span><span class="p">)</span>
<span class="go">False</span>
<span class="gp">&gt;&gt;&gt; </span><span class="n">is_pal</span><span class="p">(</span><span class="s2">&quot;010&quot;</span><span class="p">)</span>
<span class="go">True</span>
</pre></div>
</div>
</dd></dl>

<dl class="function">
<dt id="tgpc.make_eipal_closure">
<code class="descclassname">tgpc.</code><code class="descname">make_eipal_closure</code><span class="sig-paren">(</span><em>seq</em>, <em>i</em><span class="sig-paren">)</span><a class="headerlink" href="#tgpc.make_eipal_closure" title="Permalink to this definition"></a></dt>
<dd><p>Makes an Ei-palindromic closure of a string.</p>
<table class="docutils field-list" frame="void" rules="none">
<col class="field-name" />
<col class="field-body" />
<tbody valign="top">
<tr class="field-odd field"><th class="field-name">Parameters:</th><td class="field-body"><ul class="first simple">
<li><strong>seq</strong> (<em>string</em>) – A word composed
of the letters “0”, “1” and “2”.</li>
<li><strong>i</strong> – Pseudopalindromic type, can be either 0, 1, 2, or
“0”, “1”, “2”, standing for E_0, E_1 and E_2.</li>
</ul>
</td>
</tr>
<tr class="field-even field"><th class="field-name">Returns:</th><td class="field-body"><p class="first last">The palindromic closure of the word.</p>
</td>
</tr>
</tbody>
</table>
<p class="rubric">Examples</p>
<div class="highlight-default notranslate"><div class="highlight"><pre><span></span><span class="gp">&gt;&gt;&gt; </span><span class="n">make_eipal_closure</span><span class="p">(</span><span class="s2">&quot;102&quot;</span><span class="p">,</span> <span class="mi">0</span><span class="p">)</span>
<span class="go">&#39;102&#39;</span>
<span class="gp">&gt;&gt;&gt; </span><span class="n">make_eipal_closure</span><span class="p">(</span><span class="s2">&quot;101&quot;</span><span class="p">,</span> <span class="mi">1</span><span class="p">)</span>
<span class="go">&#39;10121&#39;</span>
</pre></div>
</div>
</dd></dl>

<dl class="function">
<dt id="tgpc.make_pal_closure">
<code class="descclassname">tgpc.</code><code class="descname">make_pal_closure</code><span class="sig-paren">(</span><em>seq</em><span class="sig-paren">)</span><a class="headerlink" href="#tgpc.make_pal_closure" title="Permalink to this definition"></a></dt>
<dd><p>Makes a palindromic closure of a string.</p>
<table class="docutils field-list" frame="void" rules="none">
<col class="field-name" />
<col class="field-body" />
<tbody valign="top">
<tr class="field-odd field"><th class="field-name">Parameters:</th><td class="field-body"><strong>seq</strong> (<em>string</em>) – A word.</td>
</tr>
<tr class="field-even field"><th class="field-name">Returns:</th><td class="field-body">The palindromic closure of the word.</td>
</tr>
</tbody>
</table>
<p class="rubric">Examples</p>
<div class="highlight-default notranslate"><div class="highlight"><pre><span></span><span class="gp">&gt;&gt;&gt; </span><span class="n">make_pal_closure</span><span class="p">(</span><span class="s2">&quot;101&quot;</span><span class="p">)</span>
<span class="go">&#39;101&#39;</span>
<span class="gp">&gt;&gt;&gt; </span><span class="n">make_pal_closure</span><span class="p">(</span><span class="s2">&quot;102&quot;</span><span class="p">)</span>
<span class="go">&#39;10201&#39;</span>
</pre></div>
</div>
</dd></dl>

<dl class="function">
<dt id="tgpc.make_word012">
<code class="descclassname">tgpc.</code><code class="descname">make_word012</code><span class="sig-paren">(</span><em>delta</em>, <em>theta</em>, <em>seed=''</em><span class="sig-paren">)</span><a class="headerlink" href="#tgpc.make_word012" title="Permalink to this definition"></a></dt>
<dd><p>Makes a ternary GPS word from (delta, theta).</p>
<table class="docutils field-list" frame="void" rules="none">
<col class="field-name" />
<col class="field-body" />
<tbody valign="top">
<tr class="field-odd field"><th class="field-name">Parameters:</th><td class="field-body"><ul class="first simple">
<li><strong>delta</strong> (<em>str</em>) – The sequence delta of the directive bi-sequence,
composed of the letters ‘0’, ‘1’ and ‘2’.</li>
<li><strong>theta</strong> (<em>str</em>) – The sequence theta of the directive bi-sequence,
composed from the letters ‘R’, ‘0’, ‘1’ and ‘2’, where
the last three stand for E_0, E_1 and E_2. Must have the
same length as delta.</li>
<li><strong>seed</strong> (<em>str</em>) – seed (initial w_0), optional.</li>
</ul>
</td>
</tr>
<tr class="field-even field"><th class="field-name">Returns:</th><td class="field-body"><p class="first last">A string made by pseudopalindromic closure from (delta, theta).</p>
</td>
</tr>
</tbody>
</table>
<p class="rubric">Examples</p>
<div class="highlight-default notranslate"><div class="highlight"><pre><span></span><span class="gp">&gt;&gt;&gt; </span><span class="n">make_word012</span><span class="p">(</span><span class="s2">&quot;0011&quot;</span><span class="p">,</span> <span class="s2">&quot;012R&quot;</span><span class="p">)</span>
<span class="go">&#39;00221112200&#39;</span>
</pre></div>
</div>
</dd></dl>

<dl class="function">
<dt id="tgpc.set_logging">
<code class="descclassname">tgpc.</code><code class="descname">set_logging</code><span class="sig-paren">(</span><em>logging_level='ERROR'</em><span class="sig-paren">)</span><a class="headerlink" href="#tgpc.set_logging" title="Permalink to this definition"></a></dt>
<dd><p>Sets the logging level of the module.</p>
<p>If the level is set to “ERROR”, the functions log only errors.
If it is set to “INFO” or “DEBUG”, the fuction prints more
information about how ternary words are being processed.</p>
<table class="docutils field-list" frame="void" rules="none">
<col class="field-name" />
<col class="field-body" />
<tbody valign="top">
<tr class="field-odd field"><th class="field-name">Parameters:</th><td class="field-body"><strong>level</strong> (<em>str</em>) – “ERROR” (default), “INFO” or “DEBUG”</td>
</tr>
</tbody>
</table>
</dd></dl>

</div>



    

    
  </body>
</html>
