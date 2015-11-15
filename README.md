# Tails Link boot on a MacBook Pro

This project contains files to put on the USB stick if you want to boot Tails Linux on the Macbook Pro.

**Disclaimer**: I am not a Linux boot pro and I am not a Mac boot pro. I made this by reading a lot and trying a lot. This may or may not work work for your Macbook Pro model but you may build on it if you need.

## What is the problem with Macbook Pro and Tails?

Macbook Pro boots in the UEFI mode. However Apple decided to implement UEFI specitification in its own way. For example, video BIOS is unavailable (like on "normal" computers) at proper addresses. Also when booting something, which is not OS X, Apple firmware will power up discrete graphics and make it preferable. But due to missing BIOS in UEFI mode, other OSes cannot easily use ddiscrete graphics. When Macbook Pro boots in the BootCamp (=Windows) compatible mode, video BIOS is present (emulated by the firmware).

These inconsistencies make it hard to run Linux out of the box on the Macbook Pro. Discrete graphics has to be powered down and integrated adapter should be used. This removes a possibility to use external monitors but most likely you will not need those anyway if you start Tails.

## Questions, help, etc

Sorry, I cannot answer them. As I wrote I am not a pro in this area and provide working results as is. However if you have fixes/additions for other Macbook Pro models, I would be happy to add them. Just submit a pull request.

## References

I went through many sources of information while trying to make it work. Here are some:

* [https://wiki.archlinux.org/index.php/MacBookPro8,1/8,2/8,3_(2011)#EFI_Boot]() – start here for the generic idea
* [http://ubuntuforums.org/showthread.php?t=2061791]() – most useful!
* [https://dentifrice.poivron.org/laptops/macbookpro8,2/]() – very useful when combined with info from the previous link
* [https://github.com/ndhoule/linux-on-mbp]() – intersting but for geeks, who can do their own compiling, etc. I won't risk this with Tails due to lack of knowledge
* [https://github.com/hellais/TAILS-OSX/issues/13#issuecomment-98848503]() – this gave me two crucial elements: `fakebios` and `load video`
* [https://tails.boum.org/doc/first_steps/installation/manual/mac/index.en.html]() – **bdon't do this!** It does not work at all.
* [https://github.com/0xbb/apple_set_os.efi]() – for reading only
* [https://github.com/0xbb/TAILS-OSX]() – was not directly useful but contains some info to think and build upon
