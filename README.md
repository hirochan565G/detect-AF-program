# 機械学習の決定木による心房細動の検出
<html lang="JP">
<h1>概要</h1>
  <p>2017年のPhysioNetの心電図のデータセットを使用して決定木による心房細動を検出をする。</p>
  <a href="https://physionet.org/content/challenge-2017/1.0.0/" target="_blank">AF Classification from a Short Single Lead ECG Recording - The PhysioNet Computing in Cardiology Challenge 2017:データセットのリンク先</a>
  <p>このデータセットは4つのラベルがあり、30〜60秒の短時間の心電図が記録されている。
  正常心電図であっても体動などの雑音があり、デジタルフィルタでの除去が必要になる。
  心電図にはR波と呼ばれる心室の興奮を表す波形があり、これは心臓が「ドキンドキン」と拍動していることを表している。
  R波と次のR波の間隔を心拍間隔（RRI）と呼び、これを心拍変動解析（HRV）によって時間領域分析や周波数領域分析することにより
  不整脈の特徴量となる統計量を得ることができる。
  <br>
  今回は時間領域分析を行いRRIの標準偏差であるSDNNなどを計算し、これらを特徴量としてscikit-learnの決定木による分類を行う。
    決定木は多クラス分類を行いやすく、参考文献でもストレスに対する判定がであるが、心電図へのモデルとして優秀な結果が出ている（AUC:94%）。
  周波数領域分析は2分以上のデータでなければ正確な値にならないので今回は除外する</p>
  <br>
  <h3>参考文献</h3>
  <ul>
  <li><a href="https://www.ncbi.nlm.nih.gov/pmc/articles/PMC5260487/" target="_blank">Cardiac Autonomic Dysfunction and Incidence of Atrial Fibrillation in a Large Population-Based Cohort</a></li>
  <br>
  <li><a href="https://www.ncbi.nlm.nih.gov/pmc/articles/PMC6335694/" target="_blank">Ultra-short term HRV features as surrogates of short term HRV: a case study on mental stress detection in real life</a></li>
  </ul>
<img src='./images/example_waveforms.svg'>
