> let content = NSAttributedString(String:) ->生成NSAttributedString物件

只有 NSAttributedString 可以包含圖片，一般的 String 無法，而且我們之後還會增加字串的內容，因此我們生成可以改變的 NSMutableAttributedString。(Mutable 是可以改變的意思)

> 產生包含珍奶圖片的 NSTextAttachment 物件

NSTextAttachment 可以包含圖片，之後我們將利用它生成包含圖片的 NSAttributedString

ex:let bubbleTeaAttachment = NSTextAttachment(bubbleTeaAttachment.image = UIImage(named: "Bubble_Tea_128x128"))

> 生成 NSAttributedString 時傳入 bubbleTeaAttachment，產生包含圖片的文字，然後將它加到 content 上。

content.append(NSAttributedString(attachment: bubbleTeaAttachment))

> 將 label 的 attributedText 設為 content，顯示包含圖片的文字

let label = UILabel(frame: CGRect(x: 0, y: 0, width: 200, height: 200))label.numberOfLines = 0label.attributedText = content