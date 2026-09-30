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

<AdvancedTable
  data={[
    {
      'code': 'APIKEY_EMPTY',
      'status': 'Unauthorized',
      'description': 'An API key was not supplied.',
      'message': 'You must pass in an API key.'
    },
    {
      'code': 'APIKEY_MISMATCH',
      'status': 'Forbidden',
      'description': "The API key doesn't match the project.",
      'message': "The API key doesn't match the project."
    },
    {
      'code': 'APIKEY_NOTFOUND',
      'status': 'Unauthorized',
      'description': "The API key couldn't be located.",
      'message': "We couldn't find your API key."
    },
    {
      'code': 'API_ACCESS_REVOKED',
      'status': 'Forbidden',
      'description': 'Your ReadMe API access has been revoked.',
      'message': 'Your ReadMe API access has been revoked.'
    },
    {
      'code': 'API_ACCESS_UNAVAILABLE',
      'status': 'Forbidden',
      'description': 'Your ReadMe project does not have access to this API. Please reach out to support@readme.io.',
      'message': 'Your ReadMe project does not have access to this API. Please reach out to support@readme.io.'
    },
    {
      'code': 'APPLY_INVALID_EMAIL',
      'status': 'Bad Request',
      'description': 'You need to provide a valid email.',
      'message': 'You need to provide a valid email.'
    },
    {
      'code': 'APPLY_INVALID_JOB',
      'status': 'Bad Request',
      'description': 'You need to provide a job.',
      'message': 'You need to provide a job.'
    },
    {
      'code': 'APPLY_INVALID_NAME',
      'status': 'Bad Request',
      'description': 'You need to provide a name.',
      'message': 'You need to provide a name.'
    },
    {
      'code': 'CATEGORY_INVALID',
      'status': 'Bad Request',
      'description': "The category couldn't be saved.",
      'message': "We couldn't save this category ({error})."
    },
    {
      'code': 'CATEGORY_NOTFOUND',
      'status': 'Not Found',
      'description': "The category couldn't be found.",
      'message': "The category with the slug '{category}' couldn't be found."
    },
    {
      'code': 'CHANGELOG_INVALID',
      'status': 'Bad Request',
      'description': "The changelog couldn't be saved.",
      'message': "We couldn't save this changelog ({error})."
    },
    {
      'code': 'CHANGELOG_NOTFOUND',
      'status': 'Not Found',
      'description': "The changelog couldn't be found.",
      'message': "The changelog with the slug '{slug}' couldn't be found."
    }
  ]}
/>
