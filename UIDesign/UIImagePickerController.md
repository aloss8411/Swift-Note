
UIImagePickerController -> 選擇照片

let controller = UIImagePickerController()
controller.sourceType = .photoLibrary -> 從手機圖庫抓取內容


Source Type:

public enum SourceType : Int {

	case photoLibrary

	case camera

	case savedPhotosAlbum
}