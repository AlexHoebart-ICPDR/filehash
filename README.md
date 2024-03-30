File Hash
=========

Hashes of uploaded files, which can be found on a variety of sites from
archive.org to wikileaks.org, allow files to be uniquely identified, allow
duplicate files to be detected, and allow copies to be verified against the
original source.

File Hash module generates and stores BLAKE2b-128, BLAKE2b-160, BLAKE2b-224,
BLAKE2b-256, BLAKE2b-384, BLAKE2b-512, MD5, SHA-1, SHA-224, SHA-256, SHA-384,
SHA-512/224, SHA-512/256, SHA-512, SHA3-224, SHA3-256, SHA3-384 and/or
SHA3-512 hashes for each file uploaded to the site.

Hash algorithms can be enabled and disabled by the site administrator.

Hash values are loaded into the $file object where they are available to the
theme and other modules.

Handlers are provided for Views module compatibility. In addition, a
<media:hash> element is added for file attachments in node RSS feeds (file,
image, and media field types are supported).

Tokens are provided for the full hashes, as well as pairtree tokens useful for
content addressable storage. For example, if the MD5 hash for a file is
3998b02c5cd2723153c39701683a503b, you could store it in the files/39/98
directory using these tokens:
[file:filehash-md5-pair-1]/[file:filehash-md5-pair-2]. Note, to use these tokens
to configure the file upload directory, File (Field) Paths module
(https://backdropcms.org/project/filefield_paths) is required.

A checkbox in File Hash settings allows duplicate uploaded files to be rejected.
This feature should be considered a proof-of-concept - you likely want better UX
for such a feature. Note, in Backdrop, empty files are not considered duplicate
files, as such "files" may represent remote media assets, etc.

If you want to use the BLAKE2b hash algorithm, either the Sodium PHP extension
or paragonie/sodium_compat polyfill is required.

Installation <!-- This section is required. -->
------------

- Install this module using the official Backdrop CMS instructions at
  https://docs.backdropcms.org/documentation/extend-with-modules.

- Visit the configuration page under Administration > Configuration > Media >
  File hash (admin/config/media/filehash) and enter the required information.

Issues <!-- This section is required. -->
------

Bugs and feature requests should be reported in [the Issue Queue](https://github.com/backdrop-contrib/filehash/issues).

Current Maintainers <!-- This section is required. -->
-------------------

- [Alex Hoebart](https://github.com/AlexHoebart-ICPDR)
- Seeking additional maintainers.

Credits <!-- This section is required. -->
-------

- Ported to Backdrop CMS by [Alex Hoebart](https://github.com/AlexHoebart-ICPDR)
- Originally written for Drupal by [Mark Burdett](https://github.com/mfb)

License <!-- This section is required. -->
-------

This project is GPL v2 software.
See the LICENSE.txt file in this directory for complete text.
