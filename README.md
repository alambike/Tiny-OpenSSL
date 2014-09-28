# About

Because sometimes I just need an OpenSSL wrapper that can be fatpacked.

This module is still under development.

# Synopsis

```
my $key = Tiny::OpenSSL::Key->new(
    file     => 'ca.key',
    password => 'foo',
    bits     => 4096
  );

$key->create;

my $subject = Tiny::OpenSSL::Subject->new(
    commonname          => 'My Certificate',
    organizational_unit => 'Example Company',
    organization        => 'Example Department',
    locality            => 'Austin',
    state               => 'TX',
    country             => 'US'
);

my $csr = Tiny::OpenSSL::CertificateSigningRequest->new(
    file    => 'mycert.csr',
    key     => $key,
    subject => $subject
);

$csr->create;

```


[![Build Status](https://travis-ci.org/jfwilkus/Tiny-OpenSSL.svg)](https://travis-ci.org/jfwilkus/Tiny-OpenSSL)


