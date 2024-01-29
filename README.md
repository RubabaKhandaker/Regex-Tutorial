# Regex Tutorial: Matching an Email
This guide presents a ReGex pattern designed for **email address** extraction and validation from text. An explanation is given for each component, to make said component's places within the pattern clear. The purpose of this guide is to improve knowledge and understanding regarding the use of regular expressions for email validation in various applications.

## Summary
The following ReGex will be broken down in this guide: `/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/`.

This regex aims to validate and extract email addresses from a given text. This guide will go over the 5 key components of this ReGex, namely, the start and end of the string, as well as the three capture groups (Username, Domain, and TLD).

## Table of Contents
- [Start of String](#start-of-string)
- [Capture Group One](#capture-group-one-username-and)
- [Capture Group Two](#capture-group-two-domain-name)
- [Capture Group Three](#capture-group-three-tld)
- [End of String](#end-of-string)
- [Author](#author)

# The Breakdown

## Start of String
- `^`: Asserts the start of the string. This means the pattern is meant to be read **FROM** wherever "^" is placed (left to right).

## Capture Group One (Username, and @)
- `([a-z0-9_\.-]+)`: The first capturing group. It matches one or more lowercase letters `(a-z)`, digits `(0-9)`, underscores `(_)`, dots `(.)`, and hyphens `(-)`. This makes up the username part of an email.
- `@`: Matches the at symbol, which is a required character in an email address.

## Capture Group Two (Domain name)
- `([\da-z\.-]+)`: The second capturing group. It matches one or more digits `(\d)`, lowercase letters `(a-z)`, dots `(.)`, and hyphens `(-)`. This makes up the domain name part of the email.
- `\.`: Matches a literal dot, which is required in an email address to separate the domain name from the Top-Level Domain **(TLD)**.

## Capture Group Three (TLD)
- `([a-z\.]{2,6})`: The third capturing group. It matches between 2 and 6 (as dictated by `{2,6}`) lowercase letters and dots (as dictated by `[a-z\.]`). This captures the top-level domain (TLD), which can be a country code (e.g., "us", "uk") or a generic top-level domain such as "com" or "org".

## End of String
- `$`: Asserts the end of the string. This means the pattern is meant to be read **UNTIL** wherever "$" is placed (left to right).

When combined together, the ReGex ensures that an email address follows the perscribed pattern of: `<username>@<domain>.<TLD>` by checking for valid characters in the username, domain, and TLD parts, while enforcing the presence of the at and dot symbols between them.

## Author
Rubaba Khandaker - [GitHub Profile](https://github.com/RubabaKhandaker)