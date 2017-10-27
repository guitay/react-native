---
id: version-0.39-datepickerandroid
title: datepickerandroid
original_id: datepickerandroid
---
<a id="content"></a><h1><a class="anchor" name="datepickerandroid"></a>DatePickerAndroid <a class="hash-link" href="docs/datepickerandroid.html#datepickerandroid">#</a></h1><div><div><p>Opens the standard Android date picker dialog.</p><h3><a class="anchor" name="example"></a>Example <a class="hash-link" href="docs/datepickerandroid.html#example">#</a></h3><div class="prism language-javascript"><span class="token keyword">try</span> <span class="token punctuation">{</span>
  const <span class="token punctuation">{</span>action<span class="token punctuation">,</span> year<span class="token punctuation">,</span> month<span class="token punctuation">,</span> day<span class="token punctuation">}</span> <span class="token operator">=</span> await DatePickerAndroid<span class="token punctuation">.</span><span class="token function">open<span class="token punctuation">(</span></span><span class="token punctuation">{</span>
   <span class="token comment" spellcheck="true"> // Use `new Date()` for current date.
</span>   <span class="token comment" spellcheck="true"> // May 25 2020. Month 0 is January.
</span>    date<span class="token punctuation">:</span> <span class="token keyword">new</span> <span class="token class-name">Date</span><span class="token punctuation">(</span><span class="token number">2020</span><span class="token punctuation">,</span> <span class="token number">4</span><span class="token punctuation">,</span> <span class="token number">25</span><span class="token punctuation">)</span>
  <span class="token punctuation">}</span><span class="token punctuation">)</span><span class="token punctuation">;</span>
  <span class="token keyword">if</span> <span class="token punctuation">(</span>action <span class="token operator">!</span><span class="token operator">==</span> DatePickerAndroid<span class="token punctuation">.</span>dismissedAction<span class="token punctuation">)</span> <span class="token punctuation">{</span>
   <span class="token comment" spellcheck="true"> // Selected year, month (0-11), day
</span>  <span class="token punctuation">}</span>
<span class="token punctuation">}</span> <span class="token keyword">catch</span> <span class="token punctuation">(</span><span class="token punctuation">{</span>code<span class="token punctuation">,</span> message<span class="token punctuation">}</span><span class="token punctuation">)</span> <span class="token punctuation">{</span>
  console<span class="token punctuation">.</span><span class="token function">warn<span class="token punctuation">(</span></span><span class="token string">'Cannot open date picker'</span><span class="token punctuation">,</span> message<span class="token punctuation">)</span><span class="token punctuation">;</span>
<span class="token punctuation">}</span></div></div><span><h3><a class="anchor" name="methods"></a>Methods <a class="hash-link" href="docs/datepickerandroid.html#methods">#</a></h3><div class="props"><div class="prop"><h4 class="methodTitle"><a class="anchor" name="open"></a><span class="methodType">static </span>open<span class="methodType">(options)</span> <a class="hash-link" href="docs/datepickerandroid.html#open">#</a></h4><div><p>Opens the standard Android date picker dialog.</p><p>The available keys for the <code>options</code> object are:
  <em> <code>date</code> (<code>Date</code> object or timestamp in milliseconds) - date to show by default
  </em> <code>minDate</code> (<code>Date</code> or timestamp in milliseconds) - minimum date that can be selected
  * <code>maxDate</code> (<code>Date</code> object or timestamp in milliseconds) - minimum date that can be selected</p><p>Returns a Promise which will be invoked an object containing <code>action</code>, <code>year</code>, <code>month</code> (0-11),
<code>day</code> if the user picked a date. If the user dismissed the dialog, the Promise will
still be resolved with action being <code>DatePickerAndroid.dismissedAction</code> and all the other keys
being undefined. <strong>Always</strong> check whether the <code>action</code> before reading the values.</p><p>Note the native date picker dialog has some UI glitches on Android 4 and lower
when using the <code>minDate</code> and <code>maxDate</code> options.</p></div></div><div class="prop"><h4 class="methodTitle"><a class="anchor" name="datesetaction"></a><span class="methodType">static </span>dateSetAction<span class="methodType">(0)</span> <a class="hash-link" href="docs/datepickerandroid.html#datesetaction">#</a></h4><div><p>A date has been selected.</p></div></div><div class="prop"><h4 class="methodTitle"><a class="anchor" name="dismissedaction"></a><span class="methodType">static </span>dismissedAction<span class="methodType">(0)</span> <a class="hash-link" href="docs/datepickerandroid.html#dismissedaction">#</a></h4><div><p>The dialog has been dismissed.</p></div></div></div></span></div><p class="edit-page-block">You can <a target="_blank" href="https://github.com/facebook/react-native/blob/master/Libraries/Components/DatePickerAndroid/DatePickerAndroid.android.js">edit the content above on GitHub</a> and send us a pull request!</p><div><div><table width="100%"><tbody><tr><td><h3><a class="anchor" name="examples"></a>Examples <a class="hash-link" href="docs/datepickerandroid.html#examples">#</a></h3></td><td style="text-align:right;"><a target="_blank" href="https://github.com/facebook/react-native/blob/master/Examples/UIExplorer/js/DatePickerAndroidExample.js">Edit on GitHub</a></td></tr></tbody></table><div class="example-container"><div class="prism language-javascript"><span class="token string">'use strict'</span><span class="token punctuation">;</span>

<span class="token keyword">var</span> React <span class="token operator">=</span> <span class="token function">require<span class="token punctuation">(</span></span><span class="token string">'react'</span><span class="token punctuation">)</span><span class="token punctuation">;</span>
<span class="token keyword">var</span> ReactNative <span class="token operator">=</span> <span class="token function">require<span class="token punctuation">(</span></span><span class="token string">'react-native'</span><span class="token punctuation">)</span><span class="token punctuation">;</span>
<span class="token keyword">var</span> <span class="token punctuation">{</span>
  DatePickerAndroid<span class="token punctuation">,</span>
  StyleSheet<span class="token punctuation">,</span>
  Text<span class="token punctuation">,</span>
  TouchableWithoutFeedback<span class="token punctuation">,</span>
<span class="token punctuation">}</span> <span class="token operator">=</span> ReactNative<span class="token punctuation">;</span>

<span class="token keyword">var</span> UIExplorerBlock <span class="token operator">=</span> <span class="token function">require<span class="token punctuation">(</span></span><span class="token string">'./UIExplorerBlock'</span><span class="token punctuation">)</span><span class="token punctuation">;</span>
<span class="token keyword">var</span> UIExplorerPage <span class="token operator">=</span> <span class="token function">require<span class="token punctuation">(</span></span><span class="token string">'./UIExplorerPage'</span><span class="token punctuation">)</span><span class="token punctuation">;</span>

class <span class="token class-name">DatePickerAndroidExample</span> extends <span class="token class-name">React<span class="token punctuation">.</span>Component</span> <span class="token punctuation">{</span>
  static title <span class="token operator">=</span> <span class="token string">'DatePickerAndroid'</span><span class="token punctuation">;</span>
  static description <span class="token operator">=</span> <span class="token string">'Standard Android date picker dialog'</span><span class="token punctuation">;</span>

  state <span class="token operator">=</span> <span class="token punctuation">{</span>
    presetDate<span class="token punctuation">:</span> <span class="token keyword">new</span> <span class="token class-name">Date</span><span class="token punctuation">(</span><span class="token number">2020</span><span class="token punctuation">,</span> <span class="token number">4</span><span class="token punctuation">,</span> <span class="token number">5</span><span class="token punctuation">)</span><span class="token punctuation">,</span>
    allDate<span class="token punctuation">:</span> <span class="token keyword">new</span> <span class="token class-name">Date</span><span class="token punctuation">(</span><span class="token number">2020</span><span class="token punctuation">,</span> <span class="token number">4</span><span class="token punctuation">,</span> <span class="token number">5</span><span class="token punctuation">)</span><span class="token punctuation">,</span>
    simpleText<span class="token punctuation">:</span> <span class="token string">'pick a date'</span><span class="token punctuation">,</span>
    minText<span class="token punctuation">:</span> <span class="token string">'pick a date, no earlier than today'</span><span class="token punctuation">,</span>
    maxText<span class="token punctuation">:</span> <span class="token string">'pick a date, no later than today'</span><span class="token punctuation">,</span>
    presetText<span class="token punctuation">:</span> <span class="token string">'pick a date, preset to 2020/5/5'</span><span class="token punctuation">,</span>
    allText<span class="token punctuation">:</span> <span class="token string">'pick a date between 2020/5/1 and 2020/5/10'</span><span class="token punctuation">,</span>
  <span class="token punctuation">}</span><span class="token punctuation">;</span>

  showPicker <span class="token operator">=</span> async <span class="token punctuation">(</span>stateKey<span class="token punctuation">,</span> options<span class="token punctuation">)</span> <span class="token operator">=</span><span class="token operator">&gt;</span> <span class="token punctuation">{</span>
    <span class="token keyword">try</span> <span class="token punctuation">{</span>
      <span class="token keyword">var</span> newState <span class="token operator">=</span> <span class="token punctuation">{</span><span class="token punctuation">}</span><span class="token punctuation">;</span>
      const <span class="token punctuation">{</span>action<span class="token punctuation">,</span> year<span class="token punctuation">,</span> month<span class="token punctuation">,</span> day<span class="token punctuation">}</span> <span class="token operator">=</span> await DatePickerAndroid<span class="token punctuation">.</span><span class="token function">open<span class="token punctuation">(</span></span>options<span class="token punctuation">)</span><span class="token punctuation">;</span>
      <span class="token keyword">if</span> <span class="token punctuation">(</span>action <span class="token operator">===</span> DatePickerAndroid<span class="token punctuation">.</span>dismissedAction<span class="token punctuation">)</span> <span class="token punctuation">{</span>
        newState<span class="token punctuation">[</span>stateKey <span class="token operator">+</span> <span class="token string">'Text'</span><span class="token punctuation">]</span> <span class="token operator">=</span> <span class="token string">'dismissed'</span><span class="token punctuation">;</span>
      <span class="token punctuation">}</span> <span class="token keyword">else</span> <span class="token punctuation">{</span>
        <span class="token keyword">var</span> date <span class="token operator">=</span> <span class="token keyword">new</span> <span class="token class-name">Date</span><span class="token punctuation">(</span>year<span class="token punctuation">,</span> month<span class="token punctuation">,</span> day<span class="token punctuation">)</span><span class="token punctuation">;</span>
        newState<span class="token punctuation">[</span>stateKey <span class="token operator">+</span> <span class="token string">'Text'</span><span class="token punctuation">]</span> <span class="token operator">=</span> date<span class="token punctuation">.</span><span class="token function">toLocaleDateString<span class="token punctuation">(</span></span><span class="token punctuation">)</span><span class="token punctuation">;</span>
        newState<span class="token punctuation">[</span>stateKey <span class="token operator">+</span> <span class="token string">'Date'</span><span class="token punctuation">]</span> <span class="token operator">=</span> date<span class="token punctuation">;</span>
      <span class="token punctuation">}</span>
      <span class="token keyword">this</span><span class="token punctuation">.</span><span class="token function">setState<span class="token punctuation">(</span></span>newState<span class="token punctuation">)</span><span class="token punctuation">;</span>
    <span class="token punctuation">}</span> <span class="token keyword">catch</span> <span class="token punctuation">(</span><span class="token punctuation">{</span>code<span class="token punctuation">,</span> message<span class="token punctuation">}</span><span class="token punctuation">)</span> <span class="token punctuation">{</span>
      console<span class="token punctuation">.</span><span class="token function">warn<span class="token punctuation">(</span></span>`Error <span class="token keyword">in</span> example <span class="token string">'${stateKey}'</span><span class="token punctuation">:</span> `<span class="token punctuation">,</span> message<span class="token punctuation">)</span><span class="token punctuation">;</span>
    <span class="token punctuation">}</span>
  <span class="token punctuation">}</span><span class="token punctuation">;</span>

  <span class="token function">render<span class="token punctuation">(</span></span><span class="token punctuation">)</span> <span class="token punctuation">{</span>
    <span class="token keyword">return</span> <span class="token punctuation">(</span>
      &lt;UIExplorerPage title<span class="token operator">=</span><span class="token string">"DatePickerAndroid"</span><span class="token operator">&gt;</span>
        &lt;UIExplorerBlock title<span class="token operator">=</span><span class="token string">"Simple date picker"</span><span class="token operator">&gt;</span>
          &lt;TouchableWithoutFeedback
            onPress<span class="token operator">=</span><span class="token punctuation">{</span><span class="token keyword">this</span><span class="token punctuation">.</span>showPicker<span class="token punctuation">.</span><span class="token function">bind<span class="token punctuation">(</span></span><span class="token keyword">this</span><span class="token punctuation">,</span> <span class="token string">'simple'</span><span class="token punctuation">,</span> <span class="token punctuation">{</span>date<span class="token punctuation">:</span> <span class="token keyword">this</span><span class="token punctuation">.</span>state<span class="token punctuation">.</span>simpleDate<span class="token punctuation">}</span><span class="token punctuation">)</span><span class="token punctuation">}</span><span class="token operator">&gt;</span>
            &lt;Text style<span class="token operator">=</span><span class="token punctuation">{</span>styles<span class="token punctuation">.</span>text<span class="token punctuation">}</span><span class="token operator">&gt;</span><span class="token punctuation">{</span><span class="token keyword">this</span><span class="token punctuation">.</span>state<span class="token punctuation">.</span>simpleText<span class="token punctuation">}</span>&lt;<span class="token operator">/</span>Text<span class="token operator">&gt;</span>
          &lt;<span class="token operator">/</span>TouchableWithoutFeedback<span class="token operator">&gt;</span>
        &lt;<span class="token operator">/</span>UIExplorerBlock<span class="token operator">&gt;</span>
        &lt;UIExplorerBlock title<span class="token operator">=</span><span class="token string">"Date picker with pre-set date"</span><span class="token operator">&gt;</span>
          &lt;TouchableWithoutFeedback
            onPress<span class="token operator">=</span><span class="token punctuation">{</span><span class="token keyword">this</span><span class="token punctuation">.</span>showPicker<span class="token punctuation">.</span><span class="token function">bind<span class="token punctuation">(</span></span><span class="token keyword">this</span><span class="token punctuation">,</span> <span class="token string">'preset'</span><span class="token punctuation">,</span> <span class="token punctuation">{</span>date<span class="token punctuation">:</span> <span class="token keyword">this</span><span class="token punctuation">.</span>state<span class="token punctuation">.</span>presetDate<span class="token punctuation">}</span><span class="token punctuation">)</span><span class="token punctuation">}</span><span class="token operator">&gt;</span>
            &lt;Text style<span class="token operator">=</span><span class="token punctuation">{</span>styles<span class="token punctuation">.</span>text<span class="token punctuation">}</span><span class="token operator">&gt;</span><span class="token punctuation">{</span><span class="token keyword">this</span><span class="token punctuation">.</span>state<span class="token punctuation">.</span>presetText<span class="token punctuation">}</span>&lt;<span class="token operator">/</span>Text<span class="token operator">&gt;</span>
          &lt;<span class="token operator">/</span>TouchableWithoutFeedback<span class="token operator">&gt;</span>
        &lt;<span class="token operator">/</span>UIExplorerBlock<span class="token operator">&gt;</span>
        &lt;UIExplorerBlock title<span class="token operator">=</span><span class="token string">"Date picker with minDate"</span><span class="token operator">&gt;</span>
          &lt;TouchableWithoutFeedback
            onPress<span class="token operator">=</span><span class="token punctuation">{</span><span class="token keyword">this</span><span class="token punctuation">.</span>showPicker<span class="token punctuation">.</span><span class="token function">bind<span class="token punctuation">(</span></span><span class="token keyword">this</span><span class="token punctuation">,</span> <span class="token string">'min'</span><span class="token punctuation">,</span> <span class="token punctuation">{</span>
              date<span class="token punctuation">:</span> <span class="token keyword">this</span><span class="token punctuation">.</span>state<span class="token punctuation">.</span>minDate<span class="token punctuation">,</span>
              minDate<span class="token punctuation">:</span> <span class="token keyword">new</span> <span class="token class-name">Date</span><span class="token punctuation">(</span><span class="token punctuation">)</span><span class="token punctuation">,</span>
            <span class="token punctuation">}</span><span class="token punctuation">)</span><span class="token punctuation">}</span><span class="token operator">&gt;</span>
            &lt;Text style<span class="token operator">=</span><span class="token punctuation">{</span>styles<span class="token punctuation">.</span>text<span class="token punctuation">}</span><span class="token operator">&gt;</span><span class="token punctuation">{</span><span class="token keyword">this</span><span class="token punctuation">.</span>state<span class="token punctuation">.</span>minText<span class="token punctuation">}</span>&lt;<span class="token operator">/</span>Text<span class="token operator">&gt;</span>
          &lt;<span class="token operator">/</span>TouchableWithoutFeedback<span class="token operator">&gt;</span>
        &lt;<span class="token operator">/</span>UIExplorerBlock<span class="token operator">&gt;</span>
        &lt;UIExplorerBlock title<span class="token operator">=</span><span class="token string">"Date picker with maxDate"</span><span class="token operator">&gt;</span>
          &lt;TouchableWithoutFeedback
            onPress<span class="token operator">=</span><span class="token punctuation">{</span><span class="token keyword">this</span><span class="token punctuation">.</span>showPicker<span class="token punctuation">.</span><span class="token function">bind<span class="token punctuation">(</span></span><span class="token keyword">this</span><span class="token punctuation">,</span> <span class="token string">'max'</span><span class="token punctuation">,</span> <span class="token punctuation">{</span>
              date<span class="token punctuation">:</span> <span class="token keyword">this</span><span class="token punctuation">.</span>state<span class="token punctuation">.</span>maxDate<span class="token punctuation">,</span>
              maxDate<span class="token punctuation">:</span> <span class="token keyword">new</span> <span class="token class-name">Date</span><span class="token punctuation">(</span><span class="token punctuation">)</span><span class="token punctuation">,</span>
            <span class="token punctuation">}</span><span class="token punctuation">)</span><span class="token punctuation">}</span><span class="token operator">&gt;</span>
            &lt;Text style<span class="token operator">=</span><span class="token punctuation">{</span>styles<span class="token punctuation">.</span>text<span class="token punctuation">}</span><span class="token operator">&gt;</span><span class="token punctuation">{</span><span class="token keyword">this</span><span class="token punctuation">.</span>state<span class="token punctuation">.</span>maxText<span class="token punctuation">}</span>&lt;<span class="token operator">/</span>Text<span class="token operator">&gt;</span>
          &lt;<span class="token operator">/</span>TouchableWithoutFeedback<span class="token operator">&gt;</span>
        &lt;<span class="token operator">/</span>UIExplorerBlock<span class="token operator">&gt;</span>
        &lt;UIExplorerBlock title<span class="token operator">=</span><span class="token string">"Date picker with all options"</span><span class="token operator">&gt;</span>
          &lt;TouchableWithoutFeedback
            onPress<span class="token operator">=</span><span class="token punctuation">{</span><span class="token keyword">this</span><span class="token punctuation">.</span>showPicker<span class="token punctuation">.</span><span class="token function">bind<span class="token punctuation">(</span></span><span class="token keyword">this</span><span class="token punctuation">,</span> <span class="token string">'all'</span><span class="token punctuation">,</span> <span class="token punctuation">{</span>
              date<span class="token punctuation">:</span> <span class="token keyword">this</span><span class="token punctuation">.</span>state<span class="token punctuation">.</span>allDate<span class="token punctuation">,</span>
              minDate<span class="token punctuation">:</span> <span class="token keyword">new</span> <span class="token class-name">Date</span><span class="token punctuation">(</span><span class="token number">2020</span><span class="token punctuation">,</span> <span class="token number">4</span><span class="token punctuation">,</span> <span class="token number">1</span><span class="token punctuation">)</span><span class="token punctuation">,</span>
              maxDate<span class="token punctuation">:</span> <span class="token keyword">new</span> <span class="token class-name">Date</span><span class="token punctuation">(</span><span class="token number">2020</span><span class="token punctuation">,</span> <span class="token number">4</span><span class="token punctuation">,</span> <span class="token number">10</span><span class="token punctuation">)</span><span class="token punctuation">,</span>
            <span class="token punctuation">}</span><span class="token punctuation">)</span><span class="token punctuation">}</span><span class="token operator">&gt;</span>
            &lt;Text style<span class="token operator">=</span><span class="token punctuation">{</span>styles<span class="token punctuation">.</span>text<span class="token punctuation">}</span><span class="token operator">&gt;</span><span class="token punctuation">{</span><span class="token keyword">this</span><span class="token punctuation">.</span>state<span class="token punctuation">.</span>allText<span class="token punctuation">}</span>&lt;<span class="token operator">/</span>Text<span class="token operator">&gt;</span>
          &lt;<span class="token operator">/</span>TouchableWithoutFeedback<span class="token operator">&gt;</span>
          &lt;<span class="token operator">/</span>UIExplorerBlock<span class="token operator">&gt;</span>
      &lt;<span class="token operator">/</span>UIExplorerPage<span class="token operator">&gt;</span>
    <span class="token punctuation">)</span><span class="token punctuation">;</span>
  <span class="token punctuation">}</span>
<span class="token punctuation">}</span>

<span class="token keyword">var</span> styles <span class="token operator">=</span> StyleSheet<span class="token punctuation">.</span><span class="token function">create<span class="token punctuation">(</span></span><span class="token punctuation">{</span>
  text<span class="token punctuation">:</span> <span class="token punctuation">{</span>
    color<span class="token punctuation">:</span> <span class="token string">'black'</span><span class="token punctuation">,</span>
  <span class="token punctuation">}</span><span class="token punctuation">,</span>
<span class="token punctuation">}</span><span class="token punctuation">)</span><span class="token punctuation">;</span>

module<span class="token punctuation">.</span>exports <span class="token operator">=</span> DatePickerAndroidExample<span class="token punctuation">;</span></div><div class="embedded-simulator"><p><a class="modal-button-open"><strong>Run this example</strong></a></p><div class="modal-button-open modal-button-open-img"><img alt="Run example in simulator" width="170" height="338" src="img/uiexplorer_main_android.png"></div><div><div class="modal"><div class="modal-content"><button class="modal-button-close">×</button><div class="center"><iframe class="simulator" src="https://appetize.io/embed/q7wkvt42v6bkr0pzt1n0gmbwfr?device=nexus5&amp;scale=65&amp;autoplay=false&amp;orientation=portrait&amp;deviceColor=white&amp;params=%7B%22route%22%3A%22DatePickerAndroid%22%7D" width="256" height="550" scrolling="no"></iframe><p>Powered by <a target="_blank" href="https://appetize.io">appetize.io</a></p></div></div></div><div class="modal-backdrop"></div></div></div></div></div></div><div class="docs-prevnext"><a class="docs-prev" href="docs/clipboard.html#content">← Prev</a><a class="docs-next" href="docs/dimensions.html#content">Next →</a></div>