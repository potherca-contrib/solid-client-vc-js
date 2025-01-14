# Changelog

This project adheres to [Semantic Versioning](http://semver.org/spec/v2.0.0.html).

The following changes have been implemented but not released yet:

## [Unreleased]

The following sections document changes that have been released already:

## 0.2.2 - 2021-11-26

### Bugfixes

- If getting a large response from the `/derive` endpoint, the code would freeze
  due to the response being cloned for display purpose. This is no longer the case.

## 0.2.1 - 2021-11-02

### Bugfixes

- Looking up the configuration discovery file explicitly sets the `Accept` header
  to `application/ld+json`, preventing the a`406 Unacceptable` response when trying
  to dereference it as Turtle.

## 0.2.0 - 2021-10-30

### New features

- `getVerifiableCredentialApiConfiguration`: If the VC service exposes a `.well-known/vc-configuration`
  document, this function fetches it, parses it, and returns known services from it.

## 0.1.5 - 2021-10-29

- Looking up a VC at the '/derive' endpoint was issuing incorrect requests.

## 0.1.4 - 2021-10-26

### Bugfix

- Revoking a VC was setting the revocation status to an incorrect value, preventing
  the revocation to actually happen.

## 0.1.3 - 2021-10-20

### Bugfix

- Receiving a legitimate VP could be rejected by the library if it had a single
  string as a type, which should be acceptable.

## 0.1.2 - 2021-10-13

### Bugfix

- `getVerifiableCredentialAllFromShape` expected a response format from the VC
  holder mismatching the actual response.

## 0.1.1 - 2021-09-15

### Bugfix

- No longer uses the default session from `@inrupt/solid-client-authn-browser`
  because it causes issues with Webpack.

## 0.1.0 - 2021-09-06

### New features

- Revoke a credential: the `revokeVerifiableCredential` function allows to ask
  an issuer to revoke a given credential.
- Lookup credentials at a Holder endpoint: the `getVerifiableCredentialAllFromShape`
  function collects presentations for all the VCs matching a given shape from a
  given holder.
- Request the issuance of a Verifiable Credential: the `issueVerifiableCredential`
  function requests a Verifiable Credential to be issued by a server implementing the
  W3C VC Issuer HTTP API.
