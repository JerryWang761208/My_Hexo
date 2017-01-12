---
title: '[iOS] add spinner until loading map completely'
date: 2017-01-12 09:35:08
tags:
---
Before finishing loading mapView, it's not a good user experience 
for user if there's no spinner.

We use classic spinner on the github.
i.e. 

[SVProgressHUD](https://github.com/SVProgressHUD/SVProgressHUD)

```objc
#import "SVProgressHUD.h"

-(void)viewDidLoad(){
    [super viewDidLoad];
    [SVProgressHUD show]; 
}
```

Then the keypoint is the delegation.

```objc
- (void)mapViewDidFinishRenderingMap:(MKMapView *)mapView fullyRendered:(BOOL)fullyRendered //地圖畫好後，解除spinner
{
    [SVProgressHUD dismiss];
}
```

All credit for [link](http://stackoverflow.com/questions/12967128/how-to-use-mkmapview-finished-loading-delegate-possible-finished-displaying-d)