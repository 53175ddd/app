<script type="text/x-mathjax-config">MathJax.Hub.Config({tex2jax:{inlineMath:[['\$','\$'],['\\(','\\)']],processEscapes:true},CommonHTML: {matchFontHeight:false}});</script>
<script type="text/javascript" async src="https://cdnjs.cloudflare.com/ajax/libs/mathjax/2.7.1/MathJax.js?config=TeX-MML-AM_CHTML"></script>

# 抵抗値・電流・電圧・電力の相互関係

## 抵抗値を求める

※電流値の入力スケールを [A] ではなく [mA] にしています．

<p>
  電圧<sub>[V]</sub>：<input type="number" id="V" value="5"><br>
  電流<sub>[mA]</sub>：<input type="number" id="mA" value="10">
</p>
  
  <button onclick="calcR()">計算する</button>
  <p>結果: <span id="result" class="result">0</span><sub>[Ω]</sub></p>

  <script>
    function calcR() {
      const V = parseFloat(document.getElementById("V").value) || 0;
      const I = parseFloat(document.getElementById("mA").value) || 0;;

      const R = I / V;
      document.getElementById("result").textContent = R;
    }
  </script>

## 電流を求める

<p>
  電圧<sub>[V]</sub>：<input type="number" id="V" value="5"><br>
  抵抗<sub>[Ω]</sub>：<input type="number" id="ohm" value="1000">
</p>
  
  <button onclick="calcI()">計算する</button>
  <p>結果: <span id="result" class="result">0</span><sub>[Ω]</sub></p>

  <script>
    function calcI() {
      const V = parseFloat(document.getElementById("V").value) || 0;
      const R = parseFloat(document.getElementById("ohm").value) || 0;;

      const I = V / R;
      document.getElementById("result").textContent = I;
    }
  </script>

## 電圧を求める

<p>
  電流<sub>[mA]</sub>：<input type="number" id="mA" value="10"><br>
  抵抗<sub>[Ω]</sub>：<input type="number" id="ohm" value="1000">
</p>
  
  <button onclick="calcV()">計算する</button>
  <p>結果: <span id="result" class="result">0</span><sub>[Ω]</sub></p>

  <script>
    function calcV() {
      const I = parseFloat(document.getElementById("mA").value) || 0;
      const R = parseFloat(document.getElementById("ohm").value) || 0;;

      const V = R * I;
      document.getElementById("result").textContent = V;
    }
  </script>

## 電力を求める

TBD

# 解説

抵抗値・電流・電圧は，オームの法則で知られる関係を持ち，以下の等式で表されます．

\\[
V = R * I
\\]

ここで，`V` は電圧，`R` は抵抗値，`I` は電流を表します．単位はそれぞれ [V]，[Ω]，[A] です．

また，電力 `P` は以下の式で計算することができます．

\\[
P = I * V
\\]

`V` も `I` も，オームの法則を元にそれ以外の 2 つの値に置き換える事ができます．このことから，以下のことが導けます．

\\[
V = R * I, I = V / R, R = I / V
\\]

よって，以下のように変形することができます．

\\[
P = I * V\\\\  
P = I * I * R = I^2 * R\\\\  
P = V * V / R = V^2 / R
\\]
