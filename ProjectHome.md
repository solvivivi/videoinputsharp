# VideoInputSharp #

## Description ##
VideoInputSharp is a wrapper to the [videoInput](http://muonics.net/school/spring05/videoInput/) library for .NET Framework. [videoInput](http://muonics.net/school/spring05/videoInput/) is a free windows video capture library. You can easily capture image from your devices using VideoInputSharp without additional software.

VideoInputSharpは、 [videoInput](http://muonics.net/school/spring05/videoInput/)の.NET Framework向けラッパーです。videoInputとは、DirectShowによるWindows向けのビデオキャプチャを容易に行えるライブラリです。VideoInputSharpにより、その他にライブラリを用意することなく簡単にカメラ等のデバイスからキャプチャが行えます。

![http://videoinputsharp.googlecode.com/files/capture_sample.png](http://videoinputsharp.googlecode.com/files/capture_sample.png)

## Example ##
```
using VideoInputSharp;

class Program
{
    static void Main(string[] args)
    {
        const int DeviceID = 0;

        using (VideoInput vi = new VideoInput())
        {
            vi.SetIdealFramerate(DeviceID, 30);
            vi.SetupDevice(DeviceID, 640, 480);

            byte[] buffer = new byte[vi.GetSize(DeviceID)];

            while (true)
            {
                vi.GetPixels(DeviceID, buffer);
                // do something....
            }

            vi.StopDevice(DeviceID);
        }
    }
}
```

## Requirements ##
> + **Windows**

> + **.[NET Framework 2.0](http://www.microsoft.com/downloads/details.aspx?familyid=333325FD-AE52-4E35-B531-508D977D32A6)**