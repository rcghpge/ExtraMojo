# CHANGELOG

## v0.10.0 

- Added `MovableWriter` trait so that all writers can take things that implement that, allowing them to take FileHandles, or FileDescriptors
  as well as anything else that can be written to.
- Fixed a bug in BufferedReader.read_until that would stop early if a line with just a newline (or whatever the "until" character was was hit)

## v0.9.0

- Update to Mojo 25.1.0
- Rename FileReader as BufferedReader
- Added buffered.BufferedWriter
- Added delimited.DelimWriter/DelimReader
- Added stats.ReservoirSampler
- Added cli.OptParser
- Added utils.ir.dump_ir from @soraros
- Removed benchmark module
- Added tests across the board
- Added docs across the board
- Added GH Pages docs with [modo](https://github.com/mlange-42/modo) and help from @mlange-42 - https://extramojo.github.io/ExtraMojo/
- Many small bugfixes

## v0.8.0

- Added BufferedWriter in io.buffered

## v0.7.0

- Pinned to `max == 24.6` for CI

## v0.6.0

- Moved find_chr_next_occurance to bstr.memchr and renamed it memchr and added a memchr_wide
- This also includes some small perf improvements to memchr

## v0.5.0

- Increase file reader buffer size
- Switch to memcpy internally for BufferedReader to copy bytes from buffer to line reader

## v0.4.0

- Added context manager to BufferedReader

## v0.3.2

- Do aligned reads for find next chr and to ascii lower/upper

## v0.3.1

- Added MIT and Unlincense files.

## v0.3.0

- Fixed bug in find_next_chr that didn't use the passed in start on small inputs.
- Fixed bug in BufferedReader which wasn't deallocating its buffer on deletion.
- Improved the to_ascii_lowercase perf and added a corresponding to_ascii_uppercase.
- Added more tests for all the bstr methods to better cover the different code paths based on SIMD register sizes.

## v0.2.0

- Move BufferedReader from being backed by a tensor buffer to using a raw buffer with less copies.
- Added `bstr` package with basic support for split, find, and lowercasing of byte strings (more to come!)
- Added Span api for regex's
- Deleted a lot of the Tensor related helper code
