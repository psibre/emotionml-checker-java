emotionml-checker-java
======================

[![CI](https://github.com/marytts/emotionml-checker-java/actions/workflows/main.yml/badge.svg)](https://github.com/marytts/emotionml-checker-java/actions/workflows/main.yml)
[![Maven Central](https://maven-badges.sml.io/sonatype-central/de.dfki.mary/emotionml-checker-java/badge.svg)](https://central.sonatype.com/artifact/de.dfki.mary/emotionml-checker-java)

A generic implementation of EmotionML checks, in Java.

Building
--------

Run

    ./gradlew build

Command line usage
------------------

The EmotionML checker can be used to verify the validity of a set of EmotionML files as follows:

    java -jar emotionml-checker-java.jar file.emotionml [more emotionml files]

where `file.emotionml` is an XML file containing the EmotionML document to be validated.

The tool will print for each file either an "ok" or a validation error message.

API usage
---------

Key APIs to use from Java code are the following.

To verify that a given XML document is valid EmotionML:

```java
new Checker().parse(InputStream);
new Checker().validate(Document);
new Checker().validateFragment(DocumentFragment);
```

To obtain a certain Emotion Vocabulary:

```java
EmotionVocabulary.get(String vocabularyUriWithId);
```

To inquire about properties of an Emotion Vocabulary:

```java
vocabulary.getType()
vocabulary.getItems()
```
