# Takujo-Lyric-Format
A JSON-style format for lyrics and subtitles. Highly comprehensive and customizable.

Please refer to tlf.json for sample and annotation.

Localization
All text-based contents are allowed either in String format or an array of JSON objects:

Semantics:
  "property": String
  "property": [Objects..], where the Objects should follow the format:

    {
      "content": String, // Where the actual content is
      "language": String, // Using IANA Language Subtag Registry for now
      "original": true // When the language of the song and that of the actual content, though original/official, disagree, then this object should be 1. place in the first of the array and 2. mark original to be true (default is false). 
    }

** Rule of thumb of determining the language of certain lyric lines:
  - Whichever language that has dominant word counts
  - If two languages have very close word counts, choose the language that matches the entire.

Examples:
** String:
  "title": "千本桜"

** Array:
  "singer": [
      {
        "content": "String (初音ミク)",
        "language": "jp",
      },
      {
        "content": "String (初音未来)",
        "language": "zh-Hans",
      },
      {
        "content": "String (Hatsune Miku)",
        "language": "en",
      }
