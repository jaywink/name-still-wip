# Changelog

## Unreleased

### Added

* Default power levels can now be configured in config as `rooms.power_levels` (see
  sample config file). If defined, they will be used in room creation power level
  overrides. By default, they will also be enforced on old rooms, unless
  `rooms.enforce_power_in_old_rooms` is set to `false`.

* Add config option `callbacks.unable_to_decrypt_responses` to allow disabling
  the room reply to messages that Bubo cannot decrypt.
  
* Add command `power` to set power levels in a room where the bot has the 
  required power.
  
* Add command `users` to interact with an identity provider. Currently only Keycloak
  is supported. Currently supported features is listing users and inviting new users.
  Invited users will be sent a password reset email and their email will be
  marked as verified.

### Fixed

* Don't fail to start up if `matrix.user_token` is not set (but password is).

### Removed

* Removed the `power_to_write` override in the `rooms` database table. Rooms
  can no longer for now have custom power levels enforced by Bubo on a per room basis.  

## v0.2.0 - 2020-10-30

### Added

* New command `breakout`. Allows splitting discussion into breakout rooms.

## v0.1.0 - 2020-10-24

Initial version with the following commands:
* rooms (list and create)
* communities (list and create)
* invite (self or others)
