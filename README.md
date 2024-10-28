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

5. **Repeat Steps 2–4 for `status.html`**

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