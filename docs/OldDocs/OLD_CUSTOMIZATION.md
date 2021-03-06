
**SDK Customization**
-----------------

Navigation bar
--------------

Change navigation bar color and title font color, also set left and right bar button.

    /**
     @param color Color for title bar (navigation bar). If nil default color is used.
     @param tColor Color of fonts on title bar. If nil default color is used.
     @param lColor Background color for left navigation bar button. If nil, transparent will be used.
     @param rColor Background color for right navigation bar button. If nil, transparent will be used.
     @param iPath Path to icon for button in the center of navigation bar. If nil, title will be shown, otherwise
     button will be shown. Click on button opens sub menu, which can be customized by PrintIO.
     */
    - (void)navigationBarColor:(UIColor *)color
                    titleColor:(UIColor *)tColor
     leftButtonBackgroundColor:(UIColor *)lColor
    rightButtonBackgroundColor:(UIColor *)rColor
               titleButtonIcon:(NSString *)iPath;
               
               

 Set icon for back button.

     /**
     @param path Path to image file.
     */
    - (void)iconForBackButton:(NSString *)path;

 Set status bar style and visibility. Default value is light and visible.
 
    - (void)statusBarDark:(BOOL)dark
                   hidden:(BOOL)hidden;

![enter image description here][1]

 Set three buttons Back, Menu and Cart button in navigation bar for Featured Products screen

     /**
     @param set Default value is NO
     */
    - (void)useThreeButtonsBarStyle:(BOOL)set;

Side Menu
---------

 Use Side Menu with options.
 

     /**
     @param mIconPath Path to image for Menu icon. If nil, default icon will be used.
     @param bcgColor Background color for Side Menu. If nil, default will be used.
     */
    - (void)useSideMenuWithMenuIcon:(NSString *)mIconPath
                         background:(UIColor *)bcgColor;

 Set which options to use in side menu
 

     /**
     @param buttons Array of PIOSideMenuButton objects of types:
     PIO_SM_EXIT_BUTTON,
     PIO_SM_SEARCH_BAR,
     PIO_SM_PRODUCTS,
     PIO_SM_FEATURED_PRODUCTS,
     PIO_SM_VIEW_CART,
     PIO_SM_SHARE_WITH_IMAGE,
     PIO_SM_EMAIL_SUPPORT
     
     @param options Array of PIOSideMenuButton objects of types:
     PIO_SM_CHANGE_CURRENCY,
     PIO_SM_CHANGE_COUNTRY,
     PIO_SM_CHANGE_LANGUAGE
     
     @param optionsTitle Title for this section
     @param oTitleColor Title color
     @param optionsColor Background color for this section
     @param accountsTitle Title for this section
     @param aTitleColor Title color
     @param accountsColor Background color for this section
     
     @param info Array of PIOSideMenuButton objects of types:
     PIO_SM_PRICING_CHART,
     PIO_SM_SHARE_APP,
     PIO_SM_LIKE_US_FB,
     PIO_SM_RATE_APP,
     PIO_SM_ABOUT,
     PIO_SM_HOW_IT_WORKS,
     PIO_SM_PAST_ORDERS
     
     @param infoTitle Title for this section
     @param infoTitleColor Title color
     @param infoColor Background color for this section
     
     */
    - (void)sideMenuAddButtons:(NSArray *)buttons
                       options:(NSArray *)options
                  optionsTitle:(NSString *)optionsTitle
             optionsTitleColor:(UIColor *)oTitleColor
                  optionsColor:(UIColor *)optionsColor
                 accountsTitle:(NSString *)accountsTitle
            accountsTitleColor:(UIColor *)aTitleColor
                 accountsColor:(UIColor *)accountsColor
                          info:(NSArray *)info
                     infoTitle:(NSString *)infoTitle
                infoTitleColor:(UIColor *)iTitleColor
                     infoColor:(UIColor *)infoColor
     backgroundImageForButtons:(NSString *)path;

 Slide side menu from right. Default value is NO.
 
     /**
     @param set Default value is NO
     */
     - (void)slideSideMenuFromRight:(BOOL)set;
    
    
 This is option from Side Menu, in order to use it, Side Menu needs to be enabled first.

     /**
     @param shareText Text that will be used for sharing. May contains link also.
     */
    - (void)setShareText:(NSString *)shareText;

Featured Products
-----------------

 Set country on Featured Products screen instead on First screen. Default value is NO.

    - (void)selectCountryInFeaturedProducts:(BOOL)set;

 Hide category+search view on Featured Products screen. Default value is NO;
 
    - (void)hideCategoriesInFeaturedProducts:(BOOL)hide;
    
Photo Sources
-------------

 Set available photo sources. The order of photo sources on screen will be the same like order they are placed in array.
 
     /**
     @param Array of PIOSideMenuButton objects, represents which types of photo sources will be
     available to user. Types:
     
     PIO_SM_FACEBOOK
     PIO_SM_INSTAGRAM
     PIO_SM_PICASA
     PIO_SM_FLICKR
     PIO_SM_DROPBOX
     PIO_SM_PHOTOBUCKET
     PIO_SM_PHONE
     */
    - (void)availablePhotoSources:(NSArray *)vPhotoSources;

 Pass in images URLs or UIImage objects.

     /**
     @param images Array of image urls or/and UIImage objects
     */
    - (void)images:(NSArray *)images;

 If user pass in images usinig method 'images', this method can disable photo sources,
 forcing user to use only passed photos.
 
 This method overrides method 'availablePhotoSources'

    - (void)disablePhotoSourcesWhenImagesArePassedIn:(BOOL)disable;

 Disable photo sources only if image is passed in, and user selects template with
 one photo.

    - (void)disablePhotoSourcesForOnePhotoTemplate:(BOOL)disable;

 Set passed in image to be first in row for all photo sources.

    - (void)setPassedImageFirstInPhotoSources:(BOOL)set;

 Set passed in image as thumbnail for templates with one photo.
 Right now, only supports Canvas Wraps and Framed Prints.

    - (void)setPassedImageAsThumbForOnePhotoTemplate:(BOOL)set;

 Hide icon for Upload Instructions text in Photo Sources screen. Default value is NO.

    - (void)hideIconForUplaodInstructions:(BOOL)hide;

 Set Instagram credentials. By default, PrintIO credentials are used.

    - (void)setInstagramClientID:(NSString *)clientId
                     redirectUrl:(NSString *)redirectUrl;

 Set Flickr credentials. By default, PrintIO credentials are used.

    - (void)setFlickrKey:(NSString *)key
               secretKey:(NSString *)secretKey
             redirectUrl:(NSString *)redirectUrl;

 Set Dropbox credentials. By default, PrintIO credentials are used.

    - (void)setDropboxKey:(NSString *)key
              redirectUrl:(NSString *)redirectUrl;

 Set Facebook credentials. By default, PrintIO credentials are used.

    - (void)setFacebookAppId:(NSString *)appId
                 redirectUrl:(NSString *)redirectUrl;

 Set username and password for Photobucket (autologin)

     /**
     @param userName Username or email for Photobucket account
     @param password Password
     */
     - (void)setPhotobucketUsername:(NSString *)userName
                           password:(NSString *)password;

 Set access token for Photobucket

     /**
     @param aToken Valid access token for session
     @param username Username
     */
    - (void)setPhotobucketAccessToken:(NSString *)aToken
                             userName:(NSString *)username;
                         
Customize Product
-----------------

 Show/hide tab bar in Customize Product screen. Default value is YES.

     /**
     @param show Set show/hide
     @param imagePath Path to image file.
     */
    - (void)showToolbarInCustomizeProduct:(BOOL)show
                          backgroundImage:(NSString *)imagePath;

 Hide list with images in customization screen.

    - (void)hideImagesListInCustomizeProduct:(BOOL)hide;
    
 Set photo(s) arrangement in Customize Product screen.

     /**
     @param
     PIO_PHOTO_ARRANGEMENT_CHOOSE,
     PIO_PHOTO_ARRANGEMENT_AUTO,
     PIO_PHOTO_ARRANGEMENT_MANUAL
     */
    - (void)setPhotoArrangement:(NSInteger)option;

 Change image for "Add photos" button in Customize Product screen.

     /**
     @param imagePath Path to image file.
     */
    - (void)iconForAddPhotosButton:(NSString *)imagePath;

 Change icon for Help Button on Customize Product screen.

     /**
     @param imagePath Path to image file.
     */
    - (void)iconForHelpButtonInCustomizeProduct:(NSString *)imagePath;

 Set Pop up balloon in Customize Product screen.

     /**
     @param path Path to background image.
     @param text Balloon text.
     @param textColor Text color.
    */
    - (void)setPopUpWithImage:(NSString *)path text:(NSString *)text textColor:(UIColor *)textColor;

 Show custom dialog for helping user how to edit a photo.

     /**
     @param Path to image.
     */
    - (void)showHelpDialogWithImage:(NSString *)imagePath;

Image Editor
------------

 Set which buttons will be visible in Image Editor toolbar. By default, all buttons are visible.

    /**
     @param buttons Array of PIOButton objects of types:
     PIO_BUTTON_IMAGE_EDITOR_INFO,
     PIO_BUTTON_IMAGE_EDITOR_ROTATE,
     PIO_BUTTON_IMAGE_EDITOR_EDIT_TEXT,
     PIO_BUTTON_IMAGE_EDITOR_EFFECTS
     */
    - (void)imageEditorShowButtons:(NSArray *)buttons;

Shopping Cart
-------------

 Set custom icon for Shopping Cart

     /**
     @param path Path to image file.
     @param set Set to YES if image has red circle for number of items in cart.
     */
    - (void)iconForShoppingCart:(NSString *)path withNumberOfProducts:(BOOL)set;

 Remove plus sign from "Add more products" button. By default, sign is visible.

    - (void)removePlusFromAddMoreProductsButton:(BOOL)remove;

Payment Screen
--------------

 Remove logo from Payment and Order Confirmation screen.

    - (void)removeLogoFromPaymentScreen:(BOOL)remove;

Country, Currency and Language
------------------------------

 Set country code.

    - (void)countryCode:(NSString *)countryCode;

 Set currency code.

    - (void)currencyCode:(NSString *)currencyCode;

 Set language code.

    - (void)languageCode:(NSString *)languageCode;

Steps
-----

 Jumps directly to product.

     /**
     @param productId Product identifier can be found in ProductIds.h and starts with PRODUCT_
     */
    - (void)goToProductId:(int)productId;

 Jumps directly to product with sku

     /**
     @param productId Product identifier can be found in ProductIds.h and starts with PRODUCT_
     @param sku SKU for selected product
     */
    - (void)goToProductId:(int)productId withSKU:(NSString *)sku;

 Set products variants options.

     /**
     @param options Array of PIOVariantOption objects. Pass 'color' with Case Style option
     */
    - (void)setVariantsOptions:(NSArray *)options;
    

Push Notifications
------------------

Set applicationId and apiKey provided from parse.com

     /**
     @param appId application id
 	 @param apiKey rest api key
     */
    + (void)setParseApplicationId:(NSString *)appId
                       	   apiKey:(NSString *)apiKey;
    
Register device to receive push notifications.

     /**
     @param deviceToken Device token
     */
    + (void)registerDeviceToken:(NSData *)deviceToken;
    
Display notification pop up from bottom of screen. On tap it will dismiss notification.

     /**
     @param userInfo Dictionary provided from didReceiveRemoteNotification
     @param backgroundColor Background color for notification pop up
     @param textColor Text color
     */
    + (void)showNotification:(NSDictionary *)userInfo
             backgroundColor:(UIColor *)bcgColor
                   textColor:(UIColor *)textColor;
                   
PayPal settings
-------------------

Set PayPal's client ids, for both modes, staging and production. Default values are client ids from PrintIO.

     /**
     @param sClientId Client id for staging mode
 	 @param pClientId Client id for production mode
     */
     - (void)setPayPalStagingClientId:(NSString *)sClientId
               	   productionClientId:(NSString *)pClientId;

Braintree settings
-------------------

Set Braintree encryption key for staging and production mode. By default, keys from PrintIO will be used.

    /**
    @param sEncKey Encryption key for staging mode
    @param pEncKey Encryption key for production mode
    */
    - (void)setBraintreeStagingEncryptionKey:(NSString *)sEncKey
                     productionEncryptionKey:(NSString *)pEncKey;

Other Customization
-------------------

 Import customization XML file

     /**
     @param xmlData Customization xml file.
     
     Example: NSString *xmlPath = [[NSBundle mainBundle] pathForResource:@"customization" ofType:@"xml"];
     NSData *xmlData = [NSData dataWithContentsOfFile:xmlPath];
     */
    - (void)customizationXML:(NSData *)xmlData;

 Set custom fonts from main app bundle.

     /**
     @param fonts Array of string values contain font name and type with exact order (light, medium, regular, bold). 
     
     Example: [@"font_light.otf", @"font_medium.otf", @"font_regular.otf", @"font_bold.otf"]. 
     
     Array must have four items, and fonts can be diplicated.
     */
    - (void)customFonts:(NSArray *)fonts;

 Change "Loading" GIF animation

     /**
     @param fileName File name of GIF
     */
    - (void)setLoadingGIF:(NSString *)fileName;

![enter image description here][2]

 Change title of loading dialog

     /**
     @param lText New title for loading dialog.
     */
    - (void)setLoadingText:(NSString *)lText;

 Change icon for Help Button.

     /**
     @param imagePath Path for image file
     */
    - (void)iconForHelpButton:(NSString *)imagePath;

 Change logo in SDK.

     /**
     @param logo Logo file name
     */
    - (void)changeLogo:(NSString *)logo;

 Set payee name.

     /**
     @param payeeName Payee name
     */
    - (void)payeeName:(NSString *)payeeName;

 Jumps to screen

     /**
     @param screen Screen:
            PRINTIO_SCREEN_SHOPING_CART
     */
     - (void)goToScreen:(int)screen; 

 Set url for Terms and Conditions

     /**
     @params url If not set, options will be hidden
     */
     - (void)termsAndConditionsURL:(NSURL *)url; 

Customization of UI elements in customization.xml:
--------------------------------------------------

**"Choose Country" screen**

    <customization>
        <screen name="choose_country">
           	<button name="button_no" bcg_color="#D1D1D1" font_color="#2277D4" />
            <button name="button_yes" bcg_color="#2277D4" font_color="#ffffff"/>
        </screen>
    </customization>
    
![enter image description here][3]

**“Product Details” screen**

    <customization>
        <screen name="product_details">
            <button name="button_create" bcg_color="#2277D4" font_color="#ffffff"/>
            <label name="label_1" font_color="#000000"/>
            <label name="label_2" font_color="#000000"/>
            <label name="label_3" font_color="#000000"/>
            <label name="label_4" font_color="#000000"/>
            <label name="label_5" font_color="#000000"/>
        </screen>
    </customization> 

![enter image description here][4]

**"Dialog two buttons"**

    <screen name="dialog_two_buttons">
        <button name="button_right" bcg_color="#2277D4" font_color="#ffffff"/>
        <button name="button_left" bcg_color="#D1D1D1" font_color="#2277D4"/>
    </screen>

![enter image description here][5]

**"Dialog Arrange Photos"**

    <screen name="dialog_arrange_photos">
        <button name="button_right" bcg_color="#2277D4" image_name="btn_drag_drop" image_format="png"/>
        <button name="button_left" bcg_color="#D1D1D1" image_name="btn_arrange" image_format="png"/>
        <label name="label_right" font_color="#ffffff"/>
        <label name="label_left" font_color="#2277D4"/>
    </screen>
![enter image description here][6]

**"Dialog Address Type"**

    <screen name="dialog_address_type">
        <button name="button_right" bcg_color="#2277D4" image_name="btn_home" image_format="png"/>
        <button name="button_left" bcg_color="#D1D1D1" image_name="btn_business" image_format="png"/>
        <label name="label_right" font_color="#ffffff"/>
        <label name="label_left" font_color="#2277D4"/>
    </screen>

![enter image description here][7]

**“Product image Preview” screen**

    <customization>
    	<screen name="image_preview">
            <button name="button_close" bcg_color="#ff0000" font_color="#ffffff" />
        </screen>
    </customization> 
    
![enter image description here][8]

**“Shopping Cart” screen**

    <customization>
    	<screen name="shopping_cart">
            <button name="button_check_out" bcg_color="#990022" font_color="#ffffff" />
        </screen>
    </customization>

![enter image description here][9]


----------


**5. Screen “Add Address”**

    <customization>
        	<screen name="add_address">
            	<button name="button_save" bcg_color="#446723" font_color="#ffffff" />
        	</screen>
    </customization>

![enter image description here][10]


----------


**6. Screen “Select Address”**

    <customization>
        	<screen name="select_address">
            	<button name="button_edit" bcg_color="#446723" font_color="#ffffff" />
            	<button name="button_add" bcg_color="#990022" font_color="#ffffff" />
        	</screen>
    </customization>

![enter image description here][11]


----------

**7. Screen “Address Validation”**

    <customization>
        	<screen name="address_validation">
            	<button name="button_accept" bcg_color="#446723" font_color="#ffffff" />
            	<button name="button_edit" bcg_color="#990022" font_color="#ffffff" />
            	<button name="button_edit_down" bcg_color="#990022" font_color="#ffffff" />
        	</screen>
    </customization>

![enter image description here][12]


----------

**8. Screen “Shipment Review”**

    <customization>
    	<screen name="shipment_review">
            	<button name="button_enter" bcg_color="#446723" font_color="#ffffff" />
            	<button name="button_remove" bcg_color="#553388" font_color="#ffffff" />
        	</screen>
    </customization>

![enter image description here][13]


----------

**9. Screen “Payment Methods”**

    <customization>
    	<screen name="payment_methods">
            	<button name="button_pay" bcg_color="#446723" font_color="#ffffff" />
            	<button name="button_pay_down" bcg_color="#990022" font_color="#ffffff" />
        	</screen>
    </customization>

![enter image description here][14]


----------
**10. Screen “Photo Sources”**

    <customization>
        	<screen name="photo_sources">
            	<label name="label_title" bcg_color="#ffffff" font_color="#446723" />
            	<label name="label_down" bcg_color="#990022" font_color="#ffffff" />
            	<button name="button_next" bcg_color="#446723" font_color="#ffffff" />
        	</screen>
    </customization>

![enter link description here][15]

----------

**11. Screen “Customize Product”**

    <customization>
    	<screen name="customize_product">
            	<button name="button_buy" bcg_color="#446723" font_color="#ffffff" />
            	<button name="button_back" bcg_color="#990022" font_color="#ffffff" />
    <button name="button_help" bcg_color="#990022" font_color="#ffffff" />
        	</screen>
    </customization>

![enter image description here][16]

----------

**12. Screen “Product Preview”**

    <customization>
    <screen name="product_preview">
           <label name="label_1" bcg_color="#446723" font_color="#446723" />
           <label name="label_2" bcg_color="#990022" font_color="#ffffff" />
            	<label name="label_3" bcg_color="#446723" font_color="#446723" />
            	<label name="label_4" bcg_color="#990022" font_color="#ffffff" />
            	<button name="button_back" bcg_color="#446723" font_color="#ffffff" />
            	<button name="button_edit" bcg_color="#990022" font_color="#ffffff" />
        	</screen>
    </customization>

![enter image description here][17]


----------


**13. Screen “Order Confirmation”**

    <customization>
    <screen name="order_confirmation">
            	<button name="button_close" bcg_color="#446723" font_color="#ffffff" />
        	</screen>
    </customization>

![enter image description here][18]


----------

**14. Screen “Customize Books”**

    <customization>
    	<screen name="customize_books">
            	<button name="button_back" bcg_color="#446723" font_color="#ffffff" />
            	<button name="button_buy" bcg_color="#990022" font_color="#ffffff" />
        	</screen>
    </customization>

![enter image description here][19]


----------

**15. Screen “Image Editor”**

    <customization>
    <screen name="image_editor">
            <button name="button_back" bcg_color="#446723" font_color="#ffffff" />
            <button name="button_save" bcg_color="#990022" font_color="#ffffff" />
        	</screen>
    </customization>

![enter link description here][20]


  [1]: https://lh5.googleusercontent.com/-18qrMfgPFUA/U1agy25l1aI/AAAAAAAABhI/21Bg4E2MfOY/w284-h199-no/c_sta_bar.png
  [2]: https://lh3.googleusercontent.com/-iwfn8qWXwvQ/U1ag09L9vFI/AAAAAAAABhQ/3oth_zq3NAU/w624-h483-no/c_loading.png
  [3]: https://lh6.googleusercontent.com/-eO52j3ezoBc/U3NmWmeG2HI/AAAAAAAABiI/e7_cJJq8q0U/w724-h543-no/new_1.png
  [4]: https://lh6.googleusercontent.com/-UEeaODA4QFQ/U3NuaPlAq5I/AAAAAAAABic/vx6LaUKsgMY/w665-h499-no/new_2.png
  [5]: https://lh5.googleusercontent.com/-DHjF-7ICTjM/U3NxyBrN9EI/AAAAAAAABi0/j5wEVDoD_CE/w665-h499-no/new_3.png
  [6]: https://lh4.googleusercontent.com/-z9UhSkFoMG0/U3NxydcZ8FI/AAAAAAAABjA/lPHNBXgZzrc/w665-h499-no/new_4.png
  [7]: https://lh5.googleusercontent.com/-dOZOkssFcbY/U3NxyQSwICI/AAAAAAAABi8/EDQCoh2BqtE/w665-h499-no/new_5.png
  [8]: https://lh3.googleusercontent.com/-vjkD_NIiDEU/Uuv1keaWBQI/AAAAAAAABZE/DSIRrxtNXCU/w440-h380-no/3.png
  [9]: https://lh5.googleusercontent.com/-xautWbUI1h4/U3N1ATvkreI/AAAAAAAABjY/p7gx_NNWkTA/w665-h499-no/new_6.png
  [10]: https://lh6.googleusercontent.com/-rXMwPIDrPRE/Uuv1k-ukafI/AAAAAAAABZM/rgsdzKyapgg/w417-h404-no/5.png
  [11]: https://lh4.googleusercontent.com/-aW6_mt_-wRQ/Uuv1kzZfXOI/AAAAAAAABZk/LufYhml6OPQ/w392-h377-no/6.png
  [12]: https://lh4.googleusercontent.com/-yhK7G_IHDbw/Uuv1lGwzKzI/AAAAAAAABZc/UdR3wTe5r4g/w491-h411-no/7.png
  [13]: https://lh6.googleusercontent.com/-VaVfDEGTy7Q/Uuv1lcOJRxI/AAAAAAAABZg/nNt4sIQvfwE/w457-h414-no/8.png
  [14]: https://lh5.googleusercontent.com/-IEQkIohL1x8/Uuv4li8qufI/AAAAAAAABak/Fc_sz5GXXZM/w497-h413-no/9.png
  [15]: https://lh4.googleusercontent.com/-XI9hBSfPlP0/Uuv4jIfiFpI/AAAAAAAABZ0/Tgnh0vIbexk/w475-h430-no/10.png
  [16]: https://lh5.googleusercontent.com/-6MkW6xXXX1I/Uuv4jtQWByI/AAAAAAAABaE/35vGTxX2csA/w510-h439-no/11.png
  [17]: https://lh5.googleusercontent.com/-yqOByNTVP_4/Uuv4j1F7pgI/AAAAAAAABaI/LeV-67KBJ0g/w489-h427-no/12.png
  [18]: https://lh6.googleusercontent.com/-TjmbGv4RTsY/Uuv4kKY_-KI/AAAAAAAABaM/-pO0royMH5g/w487-h410-no/13.png
  [19]: https://lh6.googleusercontent.com/-Os6CO1SseJg/Uuv4knkwGqI/AAAAAAAABaU/7Ut_TX2UbBM/w497-h429-no/14.png
  [20]: https://lh4.googleusercontent.com/-_IK-PtpI2k4/U3N5n5qD0eI/AAAAAAAABj8/0QUNDtKl9_4/w665-h499-no/SDK+Customization+%25286%2529.png
