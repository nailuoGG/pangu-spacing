## pangu-spacing.el – Minor-mode to add space between Chinese and English characters.

### Screenshot

![Screenshot](https://github.com/coldnew/pangu-spacing/raw/master/screenshot/screenshot.gif)


### Commentary (English)

pangu-spacing-mode is an minor-mode to auto add space between Chinese
and English characters.

Take following sentance for example:

     你好，我是coldnew，我喜歡使用emacs。

After you use pangu-spacing-mdoe, you will see

     你好，我是 coldnew，我喜歡使用 emacs。

This space between English and Chinese characters is called
pangu-spacing by sinologist. Since it separate the chaos between
full-width and half-width characters.

### Commentary (Chinese)


pangu-spacing-mode 是一個可以自動幫你將中文與英文之間加上`空白`作為分
隔的 minor-mode, 他的名稱來自於 paranoid-auto-spacing 上的 README。

     引述自 paranoid-auto-spacing README [1]

     如果你跟我一樣，每次看到網頁上的中文字和英文、數字、符號擠在一塊，就會
     坐立難安，忍不住想在它們之間加個空格。這個外掛（支援 Chrome 和 Firefox）
     正是你在網路世界走跳所需要的東西，它會自動替你在網頁中所有的中文字和半
     形的英文、數字、符號之間插入空白。

     漢學家稱這個空白字元為「盤古之白」，因為它劈開了全形字和半形字之間的混
     沌。另有研究顯示，打字的時候不喜歡在中文和英文之間加空格的人，感情路都
     走得很辛苦，有七成的比例會在 34 歲的時候跟自己不愛的人結婚，而其餘三成
     的人最後只能把遺產留給自己的貓。畢竟愛情跟書寫都需要適時地留白。

     與大家共勉之。ori test

     [1] https://github.com/gibuloto/paranoid-auto-spacing

### Installation


If you have `melpa` and `emacs24` installed, simply type:

     M-x package-install pangu-spacing

In your .emacs

     (require 'pangu-spacing)
     (global-pangu-spacing-mode 1)

pangu-spacing-mode do not really insert space between English and
Chinese by defaut, you should enable this option manually.

     (setq pangu-spacing-real-insert-separtor t)

If you enable this, space will be inserted before you save file.


### Function Documentation


#### `(pangu-spacing-search-buffer REGEXP START END FUNC)`

Helper macro to search buffer and do func according regexp for
pangu-spacing-mode.

#### `(pangu-spacing-search-overlay FUNC REGEXP)`

Helper macro to search and update overlay according func and regexp for
pangu-sapce-mode.

#### `(pangu-spacing-search-and-replace MATCH REGEXP)`

Replace regexp with match in buffer.

#### `(pangu-spacing-overlay-p OV)`

Determine whether overlay OV was created by space-between.

#### `(pangu-spacing-check-overlay)`

Insert a space between English words and Chinese charactors in overlay.

#### `(pangu-spacing-modify-buffer)`

Real insert separator between English words and Chinese charactors in buffer.

#### `(pangu-spacing-region-has-pangu-spacing-overlays BEG END)`

Check if region specified by BEG and END has overlay.
  Return t if it has at least one pangu-spacing overlay, nil if no overlay.

#### `(pangu-spacing-make-overlay BEG END)`

Allocate a pangu-spacing overlay in range.

#### `(pangu-spacing-delete-overlay BEG END)`

Delete all pangu-spacing-overlays in BUFFER.

#### `(pangu-spacing-delete-all-overlays)`

Delete all pangu-spacing-overlays in BUFFER.

-----
<div style="padding-top:15px;color: #d0d0d0;">
Markdown README file generated by
<a href="https://github.com/mgalgs/make-readme-markdown">make-readme-markdown.el</a>
</div>
