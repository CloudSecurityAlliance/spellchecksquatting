# Spellcheck Squatting

This is a variation on typo-squatting, mobile platforms often enable spellcheck by default which can result in user entered data being modified unexpectedly if the user is not paying attention sufficiently. An attacker can find a list of names, see what spellcheck or autocorrect suggests instead and then register the spellchecked/autocorrected  variant.

This is especially problematic in web sites and applications that allow you to send money to other users and require you to type the username/account in manually. Managing dictionaries on mobile platforms is often difficult or not possible, so adding new names may not be possible.

This also applies to capitalizing the first letter of a password by defualt, e.g. [Gmail password first character is case insensitive on mobile device](https://support.google.com/mail/thread/55577729/gmail-password-first-character-is-case-insensitive-on-mobile-device?hl=en) and the HNN thread https://news.ycombinator.com/item?id=28808289

THere is also speculation that modern code development environments that include spellcheck capabilities may introduce this issue as well for e.g. importing modules/libraries.

# Examples of this exploit

* [Sent EOS to wrong Account From exchange Coinbase](https://eosio.stackexchange.com/questions/5378/sent-eos-to-wrong-account-from-exchange-coinbase)

# Solutions:

## For web sites

Label text fields as `autocorrect="off"` and `"spellcheck="false"` in order to disable this.

## For iOS users

1. Open the Settings app
2. Tap General
3. Tap Keyboard
4. Tap the Auto-Correction toggle switch to turn it on or off

## For Android users

1. Open the Settings app
2. Tap System > Languages & input > Virtual keyboard
3. Tap Text correction
4. Go to the Corrections section and tap Auto-correction to toggle it, set it to off

## For application developers:

### Objective C

`someInput.autoCorrectionType = UITextAutocorrectionTypeNo;`

### Swift

`textField.autocorrectionType = .no`

# Finding this page

This page can be reached easily via https://spellchecksquatting.com
