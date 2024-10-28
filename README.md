# KLCiS Mikrotik Hotspot Minimalist Template OFFLINE STORE.

This is a minimalist Mikrotik hotspot template that features KLCiS e-wallet payment options for purchasing voucher codes or tickets. It supports GCash, Maya (PayMaya), and ShopeePay payment methods. Note: This payment integration is currently only available in the Philippines.

## Initial Requirements
1. A Mikrotik device configured with a hotspot server.
2. A KLCiS Trial/Active Account: [KLCiS Login](https://s2.klinternetservices.com/login)
3. Uploaded hotspot vouchers (in CSV format) to your KLCiS account. Follow this [instructional video](https://youtu.be/hSRZx8t6jJE?t=165) for uploading voucher codes.
4. A bit of creativity!

## Instructions
1. **Download the Repository**

2. **Edit the Welcome Text**
   - Open `login.html` and locate the line:
     ```html
     <h1 class="text-center text-gray mb-2 mt-2">Welcome to KEITH PISOWIFI!</h1>
     ```
   - Customize this text as desired.

3. **Edit Rates and Descriptions**
   - Update the voucher options in `login.html` based on your uploaded KLCiS voucher codes. Edit each `<option>` to reflect the correct voucher values:
     ```html
     <option value="11">₱11.00 - PROMO! 1 DAY UNLI (no pause)</option>
     <option value="5">₱5.00 - 3 HOURS (no exp.|unli pause)</option>
     <option value="10">₱10.00 - 7 HOURS (no exp.|unli pause)</option>
     <option value="20">₱20.00 - 1 day (no exp.|unli pause)</option>
     <option value="50">₱50.00 - 3 DAYS INTERNET</option>
     <option value="100">₱100.00 - 7 DAYS INTERNET</option>
     <option value="180">₱180.00 - 15 DAYS INTERNET</option>
     <option value="300">₱300.00 - 30 DAYS INTERNET</option>
     ```

4. **Set the KLCiS API Key**
   - In `login.html`, find:
     ```html
     <input type="hidden" class="form-control" id="tokenInput" name="token" value="PUT_YOUR_KLCIS_API_KEY_HERE">
     ```
   - Replace `PUT_YOUR_KLCIS_API_KEY_HERE` with your actual KLCiS API key.

5. **Repeat Steps 3–4 for `status.html and logout.html`**

6. **Customize the Banner Carousel**
   - To replace the banner images, replace `banner1.jpg` and `banner2.jpg` in the `img` folder. 
   - To add additional banners, edit `login.html`, `status.html`, and `logout.html`, and replicate this structure:
     ```html
     <div class="carousel-item active">
         <img src="img/banner1.jpg" class="d-block w-100" alt="Image 1" style="border-radius: 10px; height: auto;">
     </div>
     <div class="carousel-item">
         <img src="img/banner2.jpg" class="d-block w-100" alt="Image 2" style="border-radius: 10px; height: auto;">
     </div>
     ```

7. **Upload Files**
   - Upload the template to your Mikrotik device:
     - For **Haplite** devices, place it in the hotspot folder.
     - For **Hex** devices, place it inside the flash folder.

8. **Run the Following Commands in the Terminal**
   
   Add these entries to the Mikrotik Hotspot Walled Garden IP list to allow access to required domains:

   ```bash
   /ip hotspot walled-garden ip
   add action=accept dst-host=s2.klinternetservices.com comment="s2.klinternetservices.com"
   add action=accept dst-host=s2.klinternetservices.com comment="klinternetservices.com"
   add action=accept dst-host=payments.gcash.com comment="payments.gcash.com"
   add action=accept dst-host=gcash-api.pulseid.com comment="gcash-api.pulseid.com"
   add action=accept dst-host=beacons.gcp.gvt2.com comment="beacons.gcp.gvt2.com"
   add action=accept dst-host=irisk-sea.alipay.com comment="irisk-sea.alipay.com"
   add action=accept dst-host=mss.paas.mynt.xyz comment="mss.paas.mynt.xyz"
   add action=accept dst-host=api.mynt.xyz comment="api.mynt.xyz"
   add action=accept dst-host=login.mynt.xyz comment="login.mynt.xyz"
   add action=accept dst-host=customer-segment-api.mynt.xyz comment="customer-segment-api.mynt.xyz"
   add action=accept dst-host=gw.alipayobjects.com comment="gw.alipayobjects.com"
   add action=accept dst-host=mdap.paas.mynt.xyz comment="mdap.paas.mynt.xyz"
   add action=accept dst-host=mgs-gw.paas.mynt.xyz comment="mgs-gw.paas.mynt.xyz"
   add action=accept dst-host=ewallet-service-live.xendit.co comment="ewallet-service-live.xendit.co"
   add action=accept dst-host=checkout-ui-gateway.xendit.co comment="checkout-ui-gateway.xendit.co"
   add action=accept dst-host=checkout.xendit.co comment="checkout.xendit.co"
   add action=accept dst-host=payments.maya.ph comment="payments.maya.ph"
   add action=accept dst-host=assets.maya.ph comment="assets.maya.ph"
   add action=accept dst-host=assets.paymaya.com comment="assets.paymaya.com"
   add action=accept dst-host=api.mayabank.ph comment="api.mayabank.ph"
   add action=accept dst-host=api.paymaya.com comment="api.paymaya.com"
   add action=accept dst-host=api-bnpl.mayabank.ph comment="api-bnpl.mayabank.ph"
   add action=accept dst-host=api.xendit.co comment="api.xendit.co"
   add action=accept dst-host=connect.paymaya.com comment="connect.paymaya.com"
   add action=accept dst-host=payments.paymaya.com comment="payments.paymaya.com"
   add action=accept dst-host=cdn.growthbook.io comment="cdn.growthbook.io"
   add action=accept dst-host=d39ewjhej4wmka.cloudfront.net comment="d39ewjhej4wmka.cloudfront.net"
   add action=accept dst-host=snowplow-collector.iluma.ai comment="snowplow-collector.iluma.ai"
   add action=accept dst-host=xnd-merchant-logos.s3.amazonaws.com comment="xnd-merchant-logos.s3.amazonaws.com"
   add action=accept dst-host=snake.xendit.co.cdn.cloudflare.net comment="snake.xendit.co.cdn.cloudflare.net"

## Screenshots
![image](https://github.com/user-attachments/assets/02cc4017-1ed6-45c2-b65a-b88c509c0670)
![image](https://github.com/user-attachments/assets/bf793a17-b81e-488e-85f2-293c27e47d01)
![image](https://github.com/user-attachments/assets/dff3ce96-c1d1-4bf1-b8d4-6eb129cec293)
![logout](https://github.com/user-attachments/assets/4ae8b05c-61cb-4656-8070-105cabe437d4)
![login](https://github.com/user-attachments/assets/4873320e-1f6d-45b1-bf25-510a897cc779)






