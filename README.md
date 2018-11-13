# xcode10_libsc
适配xcode10，iOS12删除libstdc++的临时解决方案
详见项目中libsc++.zip文件，里面有库文件和对应存储的路劲。
Xcode正式版：
将压缩文件中的真机解压，放到目录：

/Applications/Xcode.app/Contents/Developer/Platforms/iPhoneOS.platform/Developer/SDKs/iPhoneOS.sdk/usr/lib/

模拟器运行：



拷贝libstdc++之后就可以编译通过了，但 App 在模拟器里一运行就崩溃，就会报动态链接库装载出错，看出错提示说是 .dylib 与这个模拟器不符合。这是 XCode10 自带的 iOS12 模拟器的问题，在 XCode10 中安装 iOS11 的模拟器运行环境，然后切换到 iOS11 模拟器运行，一切问题没有。如果想在 XCode12 iOS12 模拟器中运行：

将 libstdc++_sim.zip 解压，放到目录：/Applications/Xcode.app/Contents/Developer/Platforms/iPhoneSimulator.platform/Developer/SDKs/iPhoneSimulator.sdk/usr/lib/
b. 将 libstdc++.dylib_sim.zip 解压，放到目录：/Applications/Xcode.app/Contents/Developer/Platforms/iPhoneOS.platform/Developer/Library/CoreSimulator/Profiles/Runtimes/iOS.simruntime/Contents/Resources/RuntimeRoot/usr/lib/

