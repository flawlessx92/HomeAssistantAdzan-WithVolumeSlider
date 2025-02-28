![Home Assistant Adzan](https://user-images.githubusercontent.com/1905339/170957516-6173d318-2600-4372-bc19-b13e224272de.png)\
![visitors](https://visitor-badge.glitch.me/badge?page_id=zubir2k.homeassistantadzan.visitor-badge)
[![Donate](https://img.shields.io/badge/Donate-PayPal-green.svg)](https://www.paypal.me/zubirjamal/)

Automation for Malaysia Adzan (Muslim call to prayer) based on the following sources:
- JAKIM Official (eSolat) - [Website](https://www.e-solat.gov.my).
- AzanPro - [Website](https://api.azanpro.com).
- Home Assistant Official Islamic Prayer Time - [Website](https://www.home-assistant.io/integrations/islamic_prayer_times).

**Whats New in v4.0**
- Fully revamped eSolat sensors.
- Easy install with minimal configuration.
- Prayer time sensor will show in timestamp format. 12/24hours format are now in attributes.
- Automation are now created by default automatically. However, you may choose to create your own.
- Dynamic Media Player selector.
- Added support the official Home Assistant Islamic Prayer Time

**The Default Automation will perform the following:**
- Play TTS (for Google) or Play audio TTS (for Alexa)
- Play Azan
- Send Persistent Notification
- Send default Notification (notify.notify)

## Screenshot
![image](https://user-images.githubusercontent.com/1905339/154905774-b63319d5-4b4b-46e5-9fab-8efdeeb10400.png)

![lovelace-dashboard](https://user-images.githubusercontent.com/1905339/196147059-341c5e1d-17af-4d88-b9de-a0932759dc85.png)

![image](https://user-images.githubusercontent.com/1905339/196146905-8d58a7b5-846f-4461-8be8-73fc44eaa7da.png)

## Video Tutorial

[![Youtube](https://user-images.githubusercontent.com/1905339/170959888-079db2b3-b161-4f00-8486-af0dbbdb5aba.jpg)](https://youtu.be/DZGJwaeQuGA)
- Automation Adzan using Home Assistant: https://youtu.be/DZGJwaeQuGA
- Beginners Guide to Home Assistant: https://youtu.be/-jyegp-mL20 

## Installation
### 1. Copy all files
- Browse into your Home Assistant directory and paste all files into `\config` and `\media`.

### 2. Add eSolat into [configuration.yaml](configuration.yaml)
- Add the following line into the config file

```yaml
homeassistant:
  packages: !include_dir_named esolat/
```

- Restart Home Assistant to take effect.

### 3. Dashboard [lovelace-ui.yaml](lovelace-ui.yaml)
- Add new card, scroll at the bottom and choose Manual. 
- Copy & paste the YAML respectively.

![image](https://user-images.githubusercontent.com/1905339/196153827-56e67de2-1591-46aa-9b10-090d5dfb9633.png)

## Configure eSolat
### 1. Source
- Select source (Jakim/AzanPro/Local/Islamic Prayer Time)
- Enter state code (not applicable for Islamic Prayer Time)
- For Islamic Prayer Time, please ensure to complete the configuration in the Home Assistant Integration menu

### 2. Azan Audio & Automation
- Select your preferred media player 
- Choose your automation (Google or Alexa). Select Custom if you wish to use your own automation.
- **For Google**, please enter `azan.mp3` and `azansubuh.mp3` as your audio files. You may use your own mp3 stored in your `\media` folder.
- **For Alexa**, please enter your `home_url`. **IMPORTANT**: Please ensure [Alexa_Media_Player](https://github.com/custom-components/alexa_media_player) addon has been configured.

### 3. Refresh
- Press both Online and Local sensors to take effect.

## Special Thanks
- [@farxpeace](https://github.com/farxpeace) - for the original integration code for AzanPro
- [HomeAssistantMalaysia](https://www.facebook.com/groups/homeassistantmalaysia)

*You may also try [GPS Based](https://gist.github.com/zubir2k/04a3180f50f621c5840bbdc477d0027f) Solat sensor. (API provided by MPT)*
