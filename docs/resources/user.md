# User Resource


[Users API](https://fusionauth.io/docs/v1/tech/apis/users)

## Example Useage

```hcl
resource "fusionauth_user" "example" {
  birth_date               = "1976-05-30"
  email                    = "example@fusionauth.io"
  encryption_scheme        = "salted-sha256"
  expiry                   = 1571786483322
  first_name               = "John"
  full_name                = "John Doe"
  image_url                = "http://65.media.tumblr.com/tumblr_l7dbl0MHbU1qz50x3o1_500.png"
  last_name                = "Doe"
  middle_name              = "William"
  mobile_phone             = "303-555-1234"
  password_change_required = false
  preferred_languages = [
    "en",
    "fr"
  ]
  timezone           = "America/Denver"
  two_factor_enabled = false
  username_status    = "ACTIVE"
  username           = "johnny123"
}
```

## Argument Reference
* `tenant_id` - (Optional) The unique Id of the tenant used to scope this API request.
* `send_set_password_email` - (Optional) Indicates to FusionAuth to send the User an email asking them to set their password. The Email Template that is used is configured in the System Configuration setting for Set Password Email Template.
* `skip_verification` - (Optional) Indicates to FusionAuth that it should skip email verification even if it is enabled. This is useful for creating admin or internal User accounts.
* `birth_date` - (Optional) An ISO-8601 formatted date of the User’s birthdate such as YYYY-MM-DD.
* `data` - (Optional) An object that can hold any information about a User that should be persisted.
* `email` - (Optional) The User’s email address. An email address is a unique in FusionAuth and stored in lower case.
* `encryption_scheme` - (Optional) The method for encrypting the User’s password.
* `expiry` - (Optional) The expiration instant of the User’s account. An expired user is not permitted to login.
* `first_name` - (Optional) The first name of the User.
* `full_name` - (Optional) The User’s full name as a separate field that is not calculated from firstName and lastName.
* `image_url` - (Optional) The URL that points to an image file that is the User’s profile image.
* `last_name` - (Optional) The User’s last name.
* `middle_name` - (Optional) The User’s middle name.
* `mobile_phone` - (Optional) The User’s mobile phone number. This is useful is you will be sending push notifications or SMS messages to the User.
* `parent_email` - (Optional) The email address of the user’s parent or guardian. This field is used to allow a child user to identify their parent so FusionAuth can make a request to the parent to confirm the parent relationship.
* `password` - (Optional) The User’s plain texts password. This password will be hashed and the provided value will never be stored and cannot be retrieved.
* `password_change_required` - (Optional) Indicates that the User’s password needs to be changed during their next login attempt.
* `preferred_languages` - (Optional) An array of locale strings that give, in order, the User’s preferred languages. These are important for email templates and other localizable text.
* `timezone` - (Optional) The User’s preferred timezone. The string must be in an IANA time zone format.
* `two_factor_delivery` - (Optional) The User’s preferred delivery for verification codes during a two factor login request.
* `two_factor_enabled` - (Optional) Determines if the User has two factor authentication enabled for their account or not.
* `two_factor_secret` - (Optional) The Base64 encoded secret used to generate Two Factor verification codes.
* `username` - Optional The username of the User. The username is stored and returned as a case sensitive value, however a username is considered unique regardless of the case. bob is considered equal to BoB so either version of this username can be used whenever providing it as input to an API.
* `username_status` - (Optional) The current status of the username. This is used if you are moderating usernames via CleanSpeak.