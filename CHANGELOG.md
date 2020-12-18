# Changelog

All notable changes to this project will be documented in this file.

The format is based on [Keep a Changelog](http://keepachangelog.com/en/1.0.0/)
and this project adheres to [Semantic Versioning](http://semver.org/spec/v2.0.0.html).

## Unreleased

* Breaking Changes
  * None
* Added
  * None
* Fixed
  * None



## 6.3.0 (2020-12-17)

* Breaking Changes
  * None
* Added
  * None
* Fixed
  * [#678](https://github.com/binarylogic/authlogic/pull/678) -
    Fix `ActionText` deprecation warning by lazily loading controller adapter


## 5.0.4 (2019-09-11)

* Breaking Changes
  * None
* Added
  * None
* Fixed
  * [#681](https://github.com/binarylogic/authlogic/pull/681) -
    Delete unnecessary `AuthlogicLoadedTooLateError`


## 5.0.2 (2019-04-21)

* Breaking Changes
  * None
* Added
  * None
* Fixed
  * [#665](https://github.com/binarylogic/authlogic/pull/665) -
    Explicitly set case_sensitive: true for validates_uniqueness_of validation
    due to deprecation in Rails 6.0
  * [#659](https://github.com/binarylogic/authlogic/pull/659) -
    Fixed an issue affecting case-sensitive searches in MySQL

## 5.0.1 (2019-02-13)

* Breaking Changes
  * None
* Added
  * None
* Fixed
  * [#650](https://github.com/binarylogic/authlogic/pull/650) -
    rails 6.0.0.beta1 made a breaking change to case_insensitive_comparison

## 5.0.1 (2019-02-13)

* Breaking Changes
  * None
* Added
  * None
* Fixed
  * [#650](https://github.com/binarylogic/authlogic/pull/650) -
    rails 6.0.0.beta1 made a breaking change to case_insensitive_comparison

## 5.0.0 (2019-01-04)

* Breaking Changes
  * Likely to affect many people
    * [#629](https://github.com/binarylogic/authlogic/pull/629) -
      Drop validations deprecated in 4.4.0.
      * See [doc/use_normal_rails_validation.md][1]
      * [#640](https://github.com/binarylogic/authlogic/pull/640) -
        Drop `Authlogic::Regex`
    * [#628](https://github.com/binarylogic/authlogic/pull/628) -
      Drop `authenticates_many`, deprecated in 4.4.0
  * Likely to affect few people
    * [#617](https://github.com/binarylogic/authlogic/pull/617) -
      Drop AES-256 crypto provider, deprecated in 4.2.0
    * [#617](https://github.com/binarylogic/authlogic/pull/617) -
      Drop restful_authentication, deprecated in 4.1.0
  * Unlikely to affect anyone
    * [#647](https://github.com/binarylogic/authlogic/pull/647) -
      Drop the wordpress crypto provider, deprecated in 4.1.0
    * [#618](https://github.com/binarylogic/authlogic/pull/618) -
      Uses `frozen_string_literal`, so assume all strings returned are frozen
    * [#642](https://github.com/binarylogic/authlogic/pull/642) -
      The modules that were mixed into `Authlogic::Session::Base` have been
      inlined and deleted. This only affects you if you were re-opening
      ("monkey-patching") one of the deleted modules, in which case you can
      re-open `Base` instead.
    * [#648](https://github.com/binarylogic/authlogic/pull/648) -
      `Session::Base#credentials` now always returns a hash.
* Added
  * None
* Fixed
  * [#638](https://github.com/binarylogic/authlogic/pull/638) -
    Address Rails 5.1 changes to ActiveModel::Dirty
* Dependencies
  * [#632](https://github.com/binarylogic/authlogic/pull/632) -
    Add support for rails 6.0, drop support for rails < 5.2. See
    [doc/rails_support_in_authlogic_5.0.md](https://git.io/fpK7j) for details.
  * [#645](https://github.com/binarylogic/authlogic/pull/645) -
    Add support for ruby 2.6

## 4.4.2 (2018-09-23)

* Breaking Changes
  * None
* Added
  * None
* Fixed
  * Improved instructions in deprecation warning for validations

## 4.4.1 (2018-09-21)

* Breaking Changes
  * None
* Added
  * None
* Fixed
  * The methods for disabling Authlogic's "special" validations,
    eg. `validate_email_field = false` are actually deprecated, but should
    not produce a deprecation warning.
  * Only produce deprecation warning when configuring a validation, not when
    performing actual validation.

## 4.4.0 (2018-09-21)

* Breaking Changes
  * None
* Added
  * None
* Fixed
  * None
* Deprecation
  * [#627](https://github.com/binarylogic/authlogic/pull/627) -
    Deprecate `authenticates_many` without replacement
  * [#623](https://github.com/binarylogic/authlogic/pull/623) -
    Deprecate unnecessary validation features, use normal rails validation
    instead. See [doc/use_normal_rails_validation.md][1]

## 4.3.0 (2018-08-12)

* Breaking Changes
  * None
* Added
  * None
* Fixed
  * None
* Dependencies
  * Drop support for ruby 2.2, which reached EoL on 2018-06-20

## 4.2.0 (2018-07-18)

* Breaking Changes
  * None
* Added
  * [#611](https://github.com/binarylogic/authlogic/pull/611) - Deprecate
    AES256, guide users to choose a better crypto provider
=======
  * [#733](https://github.com/binarylogic/authlogic/pull/733) - Raisl 6.1 support
  * `find_by_login_method` is deprecated in favor of `record_selection_method`,
    to avoid confusion with ActiveRecord's "Dynamic Finders".
>>>>>>> a612f4b1f3503c7131b739a10f6f437c1c796201
* Fixed
  * [#726](https://github.com/binarylogic/authlogic/issues/726) - Thread
    safety in `Authlogic::Session::Base.klass_name`

## 6.2.0 (2020-09-03)

* Breaking Changes
  * None
* Added
  * [#684](https://github.com/binarylogic/authlogic/pull/684) - Use cookies
    only when available. Support for `ActionController::API`
* Fixed
  * [#725](https://github.com/binarylogic/authlogic/pull/725) - `NoMethodError`
    when setting `sign_cookie` or `encrypt_cookie` before `controller` is
    defined.

## 6.1.0 (2020-05-03)

* Breaking Changes
  * None
* Added
  * [#666](https://github.com/binarylogic/authlogic/pull/666) -
    Forwardported Authlogic::Session::Cookies.encrypt_cookie option
  * [#723](https://github.com/binarylogic/authlogic/pull/723) -
    Option to raise a `Authlogic::ModelSetupError` when your database is not
    configured correctly.
* Fixed
  * None

## 6.0.0 (2020-03-23)

* Breaking Changes, Major
  * There is no longer a default `crypto_provider`. We still recommend SCrypt,
    but don't want users of other providers to be forced to install it. You
    must now explicitly specify your `crypto_provider`, eg. in your `user.rb`.

        acts_as_authentic do |c|
          c.crypto_provider = ::Authlogic::CryptoProviders::SCrypt
        end

    To continue to use the `scrypt` gem, add it to your `Gemfile`.

        gem "scrypt", "~> 3.0"

* Breaking Changes, Minor
  * To set your crypto provider, you must use `crypto_provider=`, not
    `crypto_provider`. The arity of the later has changed from -1 (one optional
    arg) to 0 (no arguments).
* Added
  * [#702](https://github.com/binarylogic/authlogic/pull/702) - The ability to
    specify "None" as a valid SameSite attribute
* Fixed
  * [#686](https://github.com/binarylogic/authlogic/pull/686) - Respect
    the `log_in_after_create` setting when creating a new logged-out user
  * [#668](https://github.com/binarylogic/authlogic/pull/668) -
    BCrypt user forced to load SCrypt
  * [#697](https://github.com/binarylogic/authlogic/issues/697) - Add V2
    CryptoProviders for MD5 and SHA schemes that fix key stretching by hashing
    the byte digests instead of the hex strings representing those digests
* Dependencies
  * Drop support for ruby 2.3 (reached EOL on 2019-04-01)

## Previous major version

See eg. the `5-1-stable` branch

[1]: https://github.com/binarylogic/authlogic/blob/master/doc/use_normal_rails_validation.md
