# RainOnPane
[<img width="1920" height="1080" alt="Image" src="https://github.com/user-attachments/assets/25dc1905-511a-411f-80fb-627cca1967a2" />](https://github.com/user-attachments/assets/6b087969-c4b6-4a43-a6fd-9cd1ebd3a56f)
下の言語をクリックすると説明を展開できます。  
点击下面的语言即可展开说明。  
Click a language below to expand the documentation.

<details>
<summary><strong>日本語 - クリックして表示</strong></summary>

## 概要

**RainOnPane** は、AviUtl2 で雨に濡れた窓ガラスを再現するカスタムオブジェクトです。  
静止した雨粒、下へ流れる水、背景の屈折、雨筋、すりガラス、曇りを一つのオブジェクトで生成します。

水の先端が通過した場所では雨粒と曇りが取り除かれ、時間の経過に合わせて再付着します。  
雨筋は現在の時間から解析的に再構築されるため、タイムラインを移動した場合も同じ状態を再現できます。

RainOnPane は **「カスタムオブジェクト」** から選択できます。

## インストール方法

1. `RainOnPane_v1.0.8.au2pkg.zip` を解凍せず、AviUtl2 のプレビュー画面へドラッグ＆ドロップします。
2. 表示される内容を確認してインストールします。
3. カスタムオブジェクトを作成し、一覧から `RainOnPane` を選択します。

パッケージにはスクリプト本体と、英語・簡体中国語の表示に必要な言語ファイルが含まれています。  
表示言語は AviUtl2 の言語設定に合わせて切り替わります。

## 基本操作

RainOnPane は、処理したい背景が描画された後に配置してください。  
オブジェクトは、それ以前に描画された画面を読み取ってガラス効果を合成します。

### 雨粒

ガラスに付着する小さな雨粒と、低密度の大きな雨粒を設定します。  
密度、サイズ、更新速度、屈折を調整できます。更新速度を 0 にすると配置が静止します。

### 流れ

下へ移動する水流の数、長さ、太さ、流速、屈折を設定します。  
各水流の長さ、速度、経路、局所的な太さにはランダムな差があります。数または流速を 0 にすると水流を停止できます。

### 雨筋

水流が通過した後に残るクリアな経路を設定します。  
雨筋幅、曇り除去、雨粒除去、縁の巻込み、保持時間を調整できます。

除去は水流の下側の先端から始まり、水流の移動に合わせて経路全体へ広がります。

### 再付着

雨筋の保持時間が終了した後、曇りと雨粒が戻る速さを個別に設定します。

### ガラス

濡れ、立体感、水のボケ、ランダム、透明度、シードを設定します。  
シードを変更すると雨粒の配置と水流経路が変わり、同じ値では同じ雨の状態を再現できます。

### すりガラス

背景全体にすりガラス状の拡散を追加します。  
ぼかしと強度の初期値は 0 です。強度 100 以上では、混合率に加えて実際のぼかし半径も拡大します。

### 曇り

横方向と縦方向の 13 タップ・ガウスぼかしで、ガラスの曇りを表現します。  
ぼかしと強度の初期値は 0 です。雨粒と水流は曇りより前面に清晰に描画されます。

## 注意事項

- すりガラスと曇りは初期状態では無効です。
- 高い雨粒密度、非常に多い水流、強い曇りは GPU 負荷を増加させます。
- 雨筋は過去 12 世代の水流経路を再構築します。

</details>

<details>
<summary><strong>中文 - 点击查看</strong></summary>

## 概要

**RainOnPane** 是用于 AviUtl2 的雨窗玻璃自定义物件。  
它可以在一个对象中生成附着雨滴、向下流动的水流、背景折射、雨痕、毛玻璃和雾气。

水流前端经过的位置会清除雨滴和雾气，之后二者会随时间逐渐重新附着。  
雨痕根据当前时间进行解析重建，因此拖动时间轴后仍能得到一致的状态。

RainOnPane 可以从 **“自定义物件（カスタムオブジェクト）”** 中选择。

## 安装方法

1. 不要解压 `RainOnPane_v1.0.8.au2pkg.zip`，直接将其拖放到 AviUtl2 的预览画面。
2. 确认显示的内容后进行安装。
3. 新建自定义物件，然后从列表中选择 `RainOnPane`。

安装包包含脚本本体，以及英文和简体中文界面所需的语言文件。  
显示语言会根据 AviUtl2 的语言设置自动切换。

## 基本操作

请将 RainOnPane 放在需要处理的背景绘制完成之后。  
该对象会读取此前已经绘制的画面，再合成玻璃效果。

### 雨滴

设置附着在玻璃上的微小雨滴和较稀疏的大雨滴。  
可以调整密度、尺寸、更新速度和雨滴折射。更新速度设为 0 时，雨滴布局保持静止。

### 水流

设置向下移动的水流数量、长度、粗细、流速和折射。  
每条水流的长度、速度、路径和局部粗细都会随机变化。数量或流速设为 0 时可以关闭水流。

### 雨痕

设置水流经过后留下的清晰路径。  
可以调整雨痕宽度、雾气清除、雨滴清除、边缘卷入和雨痕保持时间。

清除从水流下方的前端开始，并随着水流移动扩展到完整路径。

### 再附着

雨痕保持时间结束后，可以分别控制雾气恢复和雨滴重新附着所需的时间。

### 玻璃

设置湿润程度、立体感、水体模糊、随机程度、透明度和随机种子。  
更改随机种子会改变雨滴布局和水流路径；相同数值可以重现相同的雨况。

### 毛玻璃

为整个背景添加毛玻璃式扩散。  
模糊和强度的默认值均为 0。强度超过 100 后，除了完整混合之外还会继续扩大实际模糊半径。

### 雾气

使用横向和纵向的 13 点高斯模糊模拟玻璃雾气。  
模糊和强度的默认值均为 0。雨滴和水流会保持在雾气前方清晰显示。

## 注意事项

- 毛玻璃和雾气默认关闭。
- 很高的雨滴密度、水流数量和雾气模糊会增加 GPU 负载。
- 雨痕会重建过去 12 代水流路径。

</details>

<details>
<summary><strong>English - Click to view</strong></summary>

## Overview

**RainOnPane** is an AviUtl2 custom object for recreating rain on a window.  
It generates attached droplets, downward-moving water streaks, background refraction, rain marks, frosted glass, and fogging in a single object.

Droplets and fogging are removed where the leading edge of a streak passes, then gradually reattach over time.  
Rain-mark history is reconstructed analytically from the current time, so timeline seeking produces a consistent state.

RainOnPane can be selected from **Custom Object (カスタムオブジェクト)**.

## Installation

1. Do not extract `RainOnPane_v1.0.8.au2pkg.zip`. Drag and drop it onto the AviUtl2 preview window.
2. Review the displayed information and install the package.
3. Create a Custom Object and select `RainOnPane` from the list.

The package includes the script and the language files required for English and Simplified Chinese UI text.  
The displayed language follows the AviUtl2 language setting.

## Basic Usage

Place RainOnPane after the background that you want to process has been drawn.  
The object reads the previously rendered frame and composites the glass effect over it.

### Droplets

Controls the dense micro-droplets and the sparser large droplets attached to the glass.  
Density, Size, Renewal Speed, and Droplet Refraction are adjustable. Setting Renewal Speed to 0 keeps the droplet layout static.

### Streaks

Controls the count, length, width, speed, and refraction of downward-moving water streaks.  
Length, speed, path, and local width vary between streaks. Setting Count or Speed to 0 disables the streaks.

### Rain marks

Controls the clear paths left after water streaks pass.  
Rain Mark Width, Fog Removal, Droplet Removal, Edge Capture, and Rain Mark Hold Time are adjustable.

Clearing begins at the lower leading edge and expands across the full path as the streak moves.

### Reattachment

Controls how quickly fogging and droplets return after the rain-mark hold time ends.

### Glass

Controls Wetness, Depth, Water Softness, Randomness, Opacity, and Seed.  
Changing Seed creates a different droplet layout and set of streak paths; the same value reproduces the same rain pattern.

### Frosted Glass

Adds frosted-glass diffusion to the entire background.  
Frost Blur and Frost Strength default to 0. Above 100, Frost Strength also increases the physical blur radius after the blend reaches full strength.

### Fogging

Uses horizontal and vertical 13-tap Gaussian blur passes to simulate fogged glass.  
Fog Blur and Fog Strength default to 0. Droplets and streaks remain clear in front of the fogged background.

## Notes

- Frosted Glass and Fogging are disabled by default.
- Very high droplet density, streak count, and fog blur increase GPU workload.
- Rain marks reconstruct the previous 12 generations of streak paths.

</details>
