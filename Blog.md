<!DOCTYPE html>
  <html lang="ja">
  <head>
      <meta charset="UTF-8">
      <meta name="viewport" content="width=device-width, initial-scale=1.0">
      <title>Cat Coding</title>

      <style>
      @charset "UTF-8";
      html {
      /* 組み方向 */
      -epub-writing-mode: vertical-rl;
      -ms-writing-mode: tb-rl;
      writing-mode: vertical-rl;
  
      orphans: 1;
      widows: 1;
      }
  
      * {
      margin: 0;
      padding: 0;
      }
  
      @page {
      size: 105mm 148mm;
      width: 88mm;
      /*  width: calc(84mm - 1q); */
      height: 110mm;
      margin-top: 20mm;
      margin-bottom: auto;
      margin-left: auto;
      margin-right: auto;
      /* 以下、マージンボックスに継承される */
      font-size: 6pt;
      font-family: "游明朝", "YuMincho", serif;
      /* 本来不要（<span class="smaller"><span class="smaller">ルート要素の指定が継承される</span></span>）だが、現時点のvivliostyle.jsの制限により必要 */
      vertical-align: top;
      }
  
      @page :left {
      margin-right: 10mm;
      @top-left {
          content: counter(page) "  <$projecttitle>";
          margin-left: 12q;
          margin-top: 135mm;
          writing-mode: horizontal-tb;
          /* CSS仕様上は@pageルール内に書けばよいが、現時点のvivliostyle.jsの制限によりここに書く */
      }
      }
      @page :right {
      margin-right: 14mm;
      /* border-bottom: 1pt solid black; */
      /* 右下ノンブル */
      @top-right {
          content: "<$fullname>   "counter(page);
          margin-right: 12q;
          margin-top: 135mm;
          writing-mode: horizontal-tb;
          /* CSS仕様上は@pageルール内に書けばよいが、現時点のvivliostyle.jsの制限によりここに書く */
      }
      }
  
      html {
      font-family: "游明朝", "YuMincho", serif;
      font-weight: Medium;
      text-align: justify;
      }
  
      body{
      }
  
      h1 {
      /* フォント */
      font-weight: Extrabold;
      /* フォントサイズ */
      font-size: 24q;
      /* 字下げ */
      text-indent: 0;
      /* 直後の改ページ・改段禁止 */
      page-break-before: always;
      page-break-after: always;
      line-height: 42q;
      letter-spacing: 0.25em;
      display: flex;
      align-items: center;
      }
  
      h2 {
      /* フォント */
      font-weight: Demibold;
      /* フォントサイズ */
      font-size: 16q;
      /* 字下げ */
      text-indent: 3em;
      /* 直後の改ページ・改段禁止 */
      page-break-before: always;
      page-break-after: avoid;
      line-height: 42q;
      margin-left: 2em;
      }
  
      h2.part {
      width: 80mm;
      padding: 0mm 35mm;
      font-weight: bold;
      font-size: 16q;
      page-break-before: always;
      page-break-after: always;
      margin-left: 4em;
      }
  
      h1 + h2 {
      margin-right: 16pt;
      }
  
      ruby > rt {
      font-size: 6.5q;
      }
  
      p {
        font-size: calc(110mm / 40);
        line height: 1.65;
        text-indent: 0em;
        hanging-punctuation: force-end;
        line-break:strict;
        page-break-inside: auto;
      }
    }
 
      div.indent-1 p:first-of-type, div.indent-2 p:first-of-type, div.indent-3 p:first-of-type{
        padding-block-start: calc( 14pt * 1.75);
        }

        div.indent-1 p:last-of-type, div.indent-2 p:last-of-type, div.indent-3 p:last-of-type{
        padding-block-end: calc( 14pt * 1.75);
        }

    
    div.indent-1 p{
    height: calc( 110mm - (14pt));
    padding-top: 14pt;
    }

    div.indent-2 p{
    height: calc( 110mm - (14pt * 2));
    padding-top: calc(14pt * 2);
    }

    div.indent-3 p{
    height: calc( 110mm - (14pt * 3));
    padding-top: calc(14pt * 3);
    }

        p.goth {
        margin-top: 3em;
        font-family: "游ゴシック", "YuGothic", san-serif;
        margin-block-start: 1em;
        margin-block-end: 1em;
        }
  
        p.align-rb {
        text-align: right;
        }

        p.goth + p.goth {
        margin-block-start: -1em;
        }

        div.codes {
        display: inline-block;
        margin: 3em 1em;
        writing-mode: horizontal-tb;
        padding: 1em;
        font-family: "Courier", monospace;
        font-size: 0.8em;
        }
  
      div.codes p {
      text-orientation: sideways;
      }
  
      p.star {
      text-indent: 3em;
      margin-right: 16pt;
      margin-left: 16pt;
      }
  
      hr {
      border: none;
      border-right: 1pt solid black;
      height: 6em;
      margin: auto 8.5pt;
      }
  
      /* 縦中横 */
      .tcy {
      -webkit-text-combine: horizontal;
      text-combine: horizontal;
      -ms-text-combine-horizontal: all;
      text-combine-horizontal: digit 2;
      text-combine-upright: digit 2;
      }
  
      /* 圏点（<span class="smaller">ゴマ</span>） */
      em.side-dot, em.sesame_dot {
      font-style: normal;
      -webkit-text-emphasis-style: sesame;
      text-emphasis-style: sesame;
      }
  
      /*著作者*/
      .author {
      position: absolute;
      bottom: 0;
      font-size: 8.5pt;
      margin-top: 50pt;
      letter-spacing: normal;
      }
  
      /*画像＋キャプション*/
      figure {
      display: block;
      width: 236pt;
      -ms-writing-mode: lr-tb;
      -webkit-writing-mode: horizontal-tb;
      writing-mode: horizontal-tb;
      }
  
      figure img {
      width: 100%;
      height: auto;
      vertical-align: bottom;
      }
  
      figcaption {
      text-align: left;
      font-size: 7pt;
      }
  
      /*奥付*/
      .colophon {
      font-size: 7pt;
      margin-right: 48pt;
      }
      /* 級さげ */
      span.smaller{
          font-size:6.5pt
      }
  
    div.comment {
        display:none;
    }

    p.blank {
        color:transparent;
    }

  @media screen{
      body {
            writing-mode: vertical-rl;
            font-family: serif;
            height: 560pt;
            overflow-y:hidden;
            padding:0;
        }
        
        #cursor {
            background-color: rgb(125,125,125,);
            animation-duration: 0.5s;
            animation-name: cursorAnimation;
            animation-iteration-count: infinite;
        }
  
        p {
            height: 560pt;
            font-family: serif;
            font-size: 14pt;
            margin:0 0 0 0;
            vertical-align: middle;
        }
          
        em.side-dot {
            font-style: normal;
            text-emphasis: filled sesame rgb(128,128,128);
            -webkit-text-emphasis: filled sesame rgb(128,128,128);
        }
        
        span.tcy {
            text-combine: horizontal;
            -webkit-text-combine:horizontal;
        }

        @keyframes cursorAnimation {
                from {
                    background-color: rgba(66,66,66,0);
                }
            
                to {
                    background-color: rgba(125,125,125,0.7);
                }
            }
  
          body{
              background-image:   linear-gradient(to right, rgba(50, 50, 50, 0.5) 0.5pt, rgba(0, 0, 50, 0.05) 10em);
              background-size:    245.73499999999999pt 560pt;
              background-repeat:  repeat-x;
              background-position: right 0px;
          }
          p{
              background-image:   linear-gradient( rgba(50, 50, 50, 1) 0.5pt, transparent 1pt),
                                  linear-gradient(to right, rgba(50, 50, 50, 1) 0.5pt, rgba(0, 0, 50, 0.05) 1pt);
              background-size:    24.5pt 14pt,
                                  24.5pt 14pt;
              background-repeat:  repeat,
                                  repeat;
              background-position: right 0px,
                                  right 0px;
          }

          div.indent-1 p{
            height: calc( 560pt - (14pt));
            padding-top: 14pt;
            }
        
            div.indent-2 p{
            height: calc( 560pt - (14pt * 2));
            padding-top: calc(14pt * 2);
            }
        
            div.indent-3 p{
            height: calc( 560pt - (14pt * 3));
            padding-top: calc(14pt * 3);
            }

        
          span.comment{
            display:block;
            border-radius:1em;
            border:1.5pt solid rgba(70,70,00,0.9);
            padding:0.25em 0.25em;
            position:absolute;
            margin-right: -3em;
            margin-top: 0.5em;
            top: 560pt;
            background-color:rgba(50,50,00,0.5);
            max-width: 20em;
          }

          span.comment::before{
            content: '';
            position: absolute;
            right: 1em;
            top: -15px;
            display: block;
            width: 0;
            height: 0;
            border-right: 15px solid transparent;
            border-bottom: 15px solid rgba(70,70,00,0.9);
            border-left: 15px solid transparent;
          }

          span.commentbody{
              margin:0.5em 1em;
              writing-mode:lr-tb;
              font-family:sans-serif;
              font-size:0.8em;
              line-height:1;
          }
  
      }
        </style>
      <link rel="stylesheet" href="">
  </head>
  <body>
  <p>　　　『VScodeにnovel-writerを導入した．』</p><p class="blank">_</p><p>　これを使えば古書なども比較的にPDF化？できるのではないかと思ったりした．</p><p>　空白や題名などをコマンドによって形式的に扱ってはいなさそうなので，LaTeXに普段から入り浸っている私にとっては，慣れが必要かなと感じた．</p><p>　一行の文字数や文字のフォントも設定から簡単に変えられそうなことは確認した．詳しくはVScodeの拡張機能の詳細を確認されたい．</p><p>　最後に，この機能の導入については「VSCodeを使った小説書きツール novel-writer がよいかんじ！」(https://note.com/rasen/n/nc4e3237051d8)を大いに参考にさせてもらった．<span id="cursor"></span></p>
  
  <script>
  
  setTimeout( (function(){
      var width = document.body.clientWidth;
      var cursor = document.getElementById('cursor');
      var panelWidth = window.innerWidth;
      var scrollEnd = cursor.offsetLeft - width + (panelWidth / 2);
      window.scrollTo( scrollEnd , scrollEnd);
      console.log(width, cursor, panelWidth, scrollEnd);
  }), 1);

</script>
  </body>
  </html>
