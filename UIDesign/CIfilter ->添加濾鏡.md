      

import CoreImage.CIFilterBuiltins

  

class ResultViewController: UITableViewController {

 @IBOutlet  weak var imageview:UIImageView!

 @IBAction func slide(_ sender: UISlider) {

 let image = UIImage(named: "image2")

 let ciImage = CIImage(image: image!)

 let filter = CIFilter.colorMonochrome()

 filter.inputImage = ciImage

 filter.intensity = sender.value

 if let outputImage = filter.outputImage{

 let*filterImage = UIImage(ciImage: outputImage)

 imageview.image = filterImage

 }

 }
 原理如下圖：
 ![[Pasted image 20210811161745.png]]