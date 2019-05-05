# NSException_ObjectiveC
NSException_ObjectiveC

``` objective-c
//
//  ViewController.m
//  NSException_ObjectiveC
//
//  Created by Carlos Santiago Cruz on 5/5/19.
//  Copyright © 2019 Carlos Santiago Cruz. All rights reserved.
//

#import "ViewController.h"

@interface ViewController ()

@end

@implementation ViewController

- (void)viewDidLoad {
    [super viewDidLoad];
    NSString *test = @"test";
    unichar a;
    int index = 5;
    @try {
        a = [test characterAtIndex:index];
    } @catch (NSException *exception) {
        NSLog(@"%@", exception.reason);
        NSLog(@"Char at index %d cannot be found", index);
        NSLog(@"Maximum index is: %lu", [test length] - 1);
    } @finally {
        NSLog(@"Finally condition");
    }
}


@end
```

``` console
2019-05-05 12:18:34.341868-0600 NSException_ObjectiveC[42599:2670878] -[__NSCFConstantString characterAtIndex:]: Range or index out of bounds
2019-05-05 12:18:34.342094-0600 NSException_ObjectiveC[42599:2670878] Char at index 5 cannot be found
2019-05-05 12:18:34.342208-0600 NSException_ObjectiveC[42599:2670878] Maximum index is: 3
2019-05-05 12:18:34.342322-0600 NSException_ObjectiveC[42599:2670878] Finally condition
```


