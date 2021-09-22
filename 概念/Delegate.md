[[*Protocol]]

>我覺得很像是告知某人（view controller）有一個權限去去操作什麼東西

delegate(代理人) & data source ->歸屬於Protocol

 ex: 要做某件事或某件事發生時,找 delegate 或 data source 幫忙,呼叫它的某個
function

本質上Delegate屬於Protocol的一種類型



class ViewController: UIViewController, UITextViewDelegate {
@IBOutlet var lyricsTextView: UITextView!
override func viewDidLoad() 
{ 
	super.viewDidLoad() 
	lyricsTextView.delegate = self
		}
	->此處的self是指controller