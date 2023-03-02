<!-- Code generated by gomarkdoc. DO NOT EDIT -->

# conv

```go
import "github.com/cloudwego/dynamicgo/conv"
```

## Index

- [Variables](<#variables>)
- [func FreeBytes(b *[]byte)](<#func-freebytes>)
- [func NewBytes() *[]byte](<#func-newbytes>)
- [type ContextKey](<#type-contextkey>)
- [type Options](<#type-options>)


## Variables

```go
var (
    // CtxKeyHTTPResponse is the key for http.ResponseSetter in context
    CtxKeyHTTPResponse = &ContextKey{}
    // CtxKeyHTTPRequest is the key for http.RequestGetter in context
    CtxKeyHTTPRequest = &ContextKey{}
    // CtxKeyThriftRespBase is the key for base.Base in context
    CtxKeyThriftRespBase = &ContextKey{}
    // CtxKeyThriftReqBase is the key for base.BaseResp in context
    CtxKeyThriftReqBase = &ContextKey{}
    // CtxKeyConvOptions is the key for Options in context
    CtxKeyConvOptions = &ContextKey{}
)
```

```go
var (
    // DefaultBufferSize is the default buffer size for conversion
    DefaultBufferSize = 4096
    // DefaultHttpValueBufferSize is the default buffer size for copying a json value
    DefaulHttpValueBufferSizeForJSON = 1024
    // DefaultHttpValueBufferSize is the default buffer size for copying a http value
    DefaulHttpValueBufferSizeForScalar = 64
)
```

## func FreeBytes

```go
func FreeBytes(b *[]byte)
```

FreeBytes returns a byte slice to pool and reset it

## func NewBytes

```go
func NewBytes() *[]byte
```

NewBytes returns a new byte slice from pool

## type ContextKey

ContextKey is the key type for context arguments

```go
type ContextKey struct {
    // contains filtered or unexported fields
}
```

## type Options

```go
type Options struct {
    // DisallowUnknownField indicates if unknown fields should be skipped
    DisallowUnknownField bool
    // WriteDefaultField indicates if default-requireness fields should be written if
    WriteDefaultField bool
    // EnableValueMapping indicates if value mapping (api.js_conv...) should be enabled
    EnableValueMapping bool
    // EnableHttpMapping indicates if http mapping (api.query|api.header...) should be enabled
    EnableHttpMapping bool
    // HttpMappingAsExtra indicates if continuing convert the same field after http mapping
    HttpMappingAsExtra bool
    // EnableThriftBase indicates if thrift/base should be recoginized and mapping to/from context
    EnableThriftBase bool
    // UseNativeSkip indicates if use thrift.SkipNative() or thrift.SkipGo()
    UseNativeSkip bool
    // Int64AsString indicates if string value cane be read as **Int8/Int16/Int32/Int64/Float64**,
    // or in response a **Int64** value can be written as string
    String2Int64 bool
    // WriteRequireField indicates if required-requireness fields should be written empty value if
    // not found
    WriteRequireField bool
    // NoBase64Binary indicates if base64 string shoud be Encode/Decode as []byte
    NoBase64Binary bool
    // ByteAsUint8 indicates if byte should be conv as uint8 (default is int8), this only works for t2j now
    ByteAsUint8 bool
    // WriteOptionalField indicates if optional-requireness fields should be written when not given
    WriteOptionalField bool
    // TracebackRequredOrRootFields indicates if required-requireness
    // or root-level fields should be seeking on http-values when reading failed from current layer of json.
    // this option is only used in j2t now.
    TracebackRequredOrRootFields bool
    // NoCopyString indicates if string should be copied or just referenced (if possible)
    NoCopyString bool
}
```



Generated by [gomarkdoc](<https://github.com/princjef/gomarkdoc>)