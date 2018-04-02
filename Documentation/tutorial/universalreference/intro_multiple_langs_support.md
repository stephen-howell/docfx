# Introduction to Multiple Languages Support

## 1. Introduction

DocFX supports generating API documentation for C# and VB natively. However, it isn't limited to these languages. DocFX is designed to support any language. When generating a document for a language, 2 steps are required: generating metadata and building documents from metadata.

## 2. Workflow

### 2.1 Generate Metadata

As different programming language have different tools written with different languages to generate API documentation, this step is not included in DocFX core. We call the tool used a **Metadata Tool**.

As [UniversalReferenceDocumentProcessor](https://github.com/dotnet/docfx/tree/dev/src/Microsoft.DocAsCode.Build.UniversalReference) is used to process these metadata files, metadata tools should generate files according the processor's input schema. It needs:
1. in YAML format and ends with `.yml` or `.yaml`
2. has YamlMime `### YamlMime:UniversalReference` at the first line
3. confirms to the [data model defined for UniversalReference](https://github.com/dotnet/docfx/tree/dev/src/Microsoft.DocAsCode.DataContracts.UniversalReference)

Usually, a TOC should generate along with YAML files for easy navigation among files.

### 2.2 Build Document

The YAML files generated are used as input of DocFX. DocFX will build these YAML files as HTML pages.

## 3. Supported Languages
* [JavaScript](gen_doc_for_js.md)
* TypeScript (coming soon ...)
* Python (coming soon ...)
