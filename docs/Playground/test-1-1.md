---
title: Test 1
deprecated: false
hidden: false
metadata:
  robots: index
---
<DeepLinkAccordion title="Test Section">
  - Lorem ipsum dolor sit amet, placeholder content for the first accordion.
</DeepLinkAccordion>

<DeepLinkAccordion title="Test Section 2">
  Same title on purpose, this checks the id auto-dedupes to test-section-1.
</DeepLinkAccordion>

<Accordion title="This is a title" icon="fa-info-circle">
  this is contents of lorem ipsum or whatever is need

  <br />

  <DeepLinkAccordion title="Test Section One">
    Lorem ipsum dolor sit amet, placeholder content for the first accordion.
  </DeepLinkAccordion>

  <DeepLinkAccordion title="Test Section Two">
    Different title from the one above, so ids stay unique without any runtime dedup logic.
  </DeepLinkAccordion>
</Accordion>

# A test heading

## Another heading

<br />

<DeepLinkAccordion title="Anchor floater">
  Lorem ipsum dolor sit amet, placeholder content for the first accordion.
</DeepLinkAccordion>

<DeepLinkAccordion title="Awesome anchor">
  Lorem ipsum dolor sit amet, placeholder content for the first accordion.
</DeepLinkAccordion>

<DeepLinkAccordion title="SVG Anchor">
  Lorem ipsum dolor sit amet, placeholder content for the first accordion.
</DeepLinkAccordion>

<DeepLinkAccordion title="SVG awesome">
  Lorem ipsum dolor sit amet, placeholder content for the first accordion.
</DeepLinkAccordion>

<DeepLinkAccordion title="Correct SVG awesome">
  Lorem ipsum dolor sit amet, placeholder content for the first accordion.
</DeepLinkAccordion>

<DeepLinkAccordion title="Test Section One">
  Lorem ipsum dolor sit amet, placeholder content for the first accordion.
</DeepLinkAccordion>

<DeepLinkAccordion title="Now with copied to clipboard">
  Different title from the one above, so ids stay unique without any runtime dedup logic.
</DeepLinkAccordion>

|   |   |   |
| - | - | - |
|   |   |   |
|   |   |   |

<AdvancedAccordion title="Test Section One" editable>
  Lorem ipsum dolor sit amet, placeholder content for the first accordion.
</AdvancedAccordion>

<AdvancedAccordion title="Test Section One" editable>
  Lorem ipsum dolor sit amet, placeholder content for the first accordion.
</AdvancedAccordion>
