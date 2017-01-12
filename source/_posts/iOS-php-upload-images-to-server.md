---
title: '[iOS & php] upload images to server'
date: 2016-12-28 18:46:39
tags:
---
Images uploading is general for user.

I'm writing iOS project using Objective-c and server side
is php.

``` objc

   UIImage *image = [UIImage imageNamed:@"joker.png"];  // name of the image
    
    NSData *imageData =  UIImagePNGRepresentation(image);  // convert your image into data
    
    NSString *urlString = [NSString stringWithFormat:@"YOUR URL"];  // enter your url to upload
  
    AFHTTPSessionManager *manager = [AFHTTPSessionManager manager];  // allocate AFHTTPManager
    
    [manager POST:urlString parameters:nil constructingBodyWithBlock:^(id<AFMultipartFormData> formData) {  // POST DATA USING MULTIPART CONTENT TYPE
        [formData appendPartWithFileData:imageData
                                    name:@"file"
                                fileName:@"image.jpg" mimeType:@"image/jpeg"];   // add image to formData
        
        [formData appendPartWithFormData:[@"sdsd" dataUsingEncoding:NSUTF8StringEncoding]
                                    name:@"key1"];    // add your other keys !!! 
      
    } progress:nil success:^(NSURLSessionDataTask *task, id responseObject) {
        NSLog(@"Response: %@", responseObject);    // Get response from the server
        
        
        
    } failure:^(NSURLSessionDataTask *task, NSError *error) {
        NSLog(@"Error: %@", error);   // Gives Error
      
    }]

```
You could change parameters if it's not nil.

The above is credit for : [link](http://codeobjectivec.blogspot.tw/2016/04/upload-image-file-to-server-in-ios.html) 

``` php
//images upload ios
	public function upload() {
		$name = $_FILES['file']['name'];
		$tmp_name = $_FILES['file']['tmp_name'];
		$type = $_FILES['file']['type'];
		$size = $_FILES['file']['size'];

```

forgive me the php part, it's my company project which is privacy.

Just beware that 

``` php
name:@"file"   $_FILES['file']
```
the name "file" should be the same.

And while in Android, you should use base64 in php.

