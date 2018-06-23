# samsung-smartthings-hub
Using the Samsung Smart Things Hub in Australia - a HOWTO

## Background

The Samsung Smart Things hub is not available for purchase in Australia.  The primary reason seems to the fact that the hub offers both [Zigbee](http://www.zigbee.org/) and [Z-Wave](http://www.z-wave.com/).  Whilst Zigbee products are available locally, it seems that Z-Wave products are not - or at least the common ones are not.

Most likely this is due to the standard radio frequencies that most Z-Wave products use.  They are restricted in Australia, and **using them would be illegal**.

You can't blame Samsung for going out of their way to inconvience you trying to get it to work.

## So I can't use the Smart Things hub in Australia?

Well, the hub does support disabling the Z-Wave function - which is my recommendation if you want to proceed with enabling the hub and associated mobile app.

For my purposes, Z-Wave is not required - I just want to control Philips Hue bulbs and some [Xiaomi Mi Smart Sockets Plugs](https://xiaomi-mi.com/sockets-and-sensors/xiaomi-mi-smart-socket-plug-2-zigbee-edition-white/).  In the short term additional smart devices I'm considering are all available as Zigbee devices.

## Buying a suitable Samsung Smart Things hub

I purchased one from the UK.  The reason being that the voltage requirements of the DC PSU are the same at ~240v.  This saves you finding a local replacement PSU instead of a straight forward travel adapter.

Also, the UK tends to be closer aligned to Australia when it comes to regulations, i.e. frequencies allowed for public use.

## Most important step

Firstly, if you have a [Samsung Account](https://account.samsung.com/) and you're reading this - it is likely to be an Australian region account.  There is no way to change the region of an existing account, so you **will have to create a new account**.

Samsung implement geo-blocking, and forcibly direct you to the relevant Samsung global site for account registration.  Generally this is fine, but in this case it is not what you want.

To ensure you set up a UK account:

1. Download the [Tor Browser](https://www.torproject.org/projects/torbrowser.html)
1. Install the browser
1. Run the browser, and visit the Smart Things IDE (API) site https://graph-eu01-euwest1.api.smartthings.com/
1. Choose to create an account
1. Ensure that the region/language at bottom of page is set to United Kingdom/English
1. Proceed with setting up you account as normal
1. Copy the validation link in the email you recieve, and **paste it into your Tor Browser**

The point of using the Tor browser, is that your request to the Samsung site will appear to originate in Europe.  Details on how Tor works are [here](https://www.torproject.org/about/overview.html.en).  You can achieve the same thing using a UK/European VPN, but you're likely to need to pay for that.

## I have to stop using my normal Samsung account?

Yes.  At least until you've set up for your hub.  My phone (a Samsung Galaxy S8) will only allow one Samsung account to be associated with the device.

If you choose to switch between your existing account, and the new one - bear in mind that you will need to use the UK account when you want to add new devices, and possible operate the devices you've added (I've not verified that).

I'm not keen on switching back and forth, so this new account is now my primary one.  Having an European account can't hurt - you are likely to benefit from better respect for privacy, i.e. the [GDPR](https://www.eugdpr.org/).

## Set your phone Samsung Account

Remove your existing account by accessing (on your phone) the `Settings` > `Cloud and accounts` > `Accounts` > `Samsung Account`.  Choose the menu option to `Remove account`.

Now, add you new UK account.

## Register the Samsung Smart Things Hub

Make sure that if you've been running the Smart Things app that it is closed.  You should clean out any saved and cached data.  You can do this by going to `Settings` > `Apps` then locating the `SmartThings` app. Choose `Force Stop`, then from the `Storage` option `Clear Data` and `Clear Cache`.

Run the SmartThings application, then choose `Add Device`.  If the above steps have worked, you should be able to choose to manually add device, and select `Hubs`.

If you're account was not successfully registered to the correct region, the Hubs option will be missing.

## Important Post-Registration Step

Once you have the hub added you should disable the Z-Wave function.  Not doing so is both illegal, and highly irresponsible as the frequency is used by mobile phone networks in Australia.

You can do so by accessing the IDE/API at https://graph-eu01-euwest1.api.smartthings.com/ then selecting `My Hubs` then `View Utilities`.  From there select `Disable Z-Wave Module`.

## Anthing else?

No that's it.  I have integrated mine with my Amazon Echo and will likely look at further automation opportunites, preferably home-hosted rather than cloud.

If you found this helpful, please **Star** this project.
