# ImageSelectedFromPictureLibrary
//选在相册里的图片放在imageView里面


    @IBAction func selectImageFromPhotoLibrary(sender: UITapGestureRecognizer) {
        mealNameTextField.resignFirstResponder()
        let imagePickerController = UIImagePickerController()
        imagePickerController.sourceType = .PhotoLibrary
        imagePickerController.delegate = self
        presentViewController(imagePickerController, animated: true, completion: nil)
    }
    
    func imagePickerControllerDidCancel(picker: UIImagePickerController) {
        dismissViewControllerAnimated(true, completion: nil)
    }
    
    func imagePickerController(picker: UIImagePickerController, didFinishPickingMediaWithInfo info: [String : AnyObject]) {
        let selectImage = info[UIImagePickerControllerOriginalImage] as! UIImage
        imageView1.image = selectImage
        dismissViewControllerAnimated(true, completion: nil)
    }

