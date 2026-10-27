# Real Estate Social Media Post Agent

A sanitized n8n workflow export based on a real real-estate social content automation.

## What it does

- Receives a property-post request through a webhook.
- Summarizes supplied property facts and visual instructions.
- Generates an image prompt and calls an image-generation API.
- Creates separate Facebook, TikTok, and LinkedIn captions.
- Requests human approval by email.
- Writes approved content to Google Sheets.
- Uses Cloudinary and Buffer API requests for image handling and social publishing.

## Important setup before importing

This is a **sanitized workflow export**, not a plug-and-play deployment. Before running it:

1. Configure your OpenAI credentials in the model nodes.
2. Replace the KIE API token placeholder in the image-generation HTTP Request node.
3. Configure the Google Sheets document ID and connect your Google Sheets account.
4. Configure the approver email and connect Gmail.
5. Configure Cloudinary cloud name/upload preset and confirm your upload preset's security settings.
6. Replace Buffer channel ID placeholders and configure the Buffer API token.
7. Replace the example owner-image URL with an image URL you have permission to use.
8. Test with a non-public draft before enabling publishing.

The original export contained API tokens, credential references, account identifiers, sample contact information, and pinned execution data. Those values have been removed or replaced with placeholders. No live credentials are included.

## Known limitations

- The export should be reviewed and tested in your n8n version before production use.
- The prompt asks the image model to preserve a fixed owner image, but prompt text alone cannot guarantee pixel-identical compositing. Use a deterministic image overlay/compositing step if exact preservation is required.
- The exported connections should be tested against the incoming `platforms` and `action` values; do not assume those fields are enforced as routing conditions.
- Approval/rejection paths, image callback handling, API failures, and actual social publishing must be tested with your own connected accounts.

## Files

- `workflow.json` — sanitized n8n workflow export.

## License and privacy

This is provided as a portfolio/reference workflow. Review the node prompts, connected services, third-party API terms, and data-handling requirements before reuse.
