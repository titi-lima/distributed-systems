# AGENTS Notes

## Cisco Packet Tracer workflow

When editing `deliverables/topologia.pkt`, Packet Tracer was unstable if treated like a normal text or terminal-driven tool. The safest workflow was:

- Open the existing `.pkt` and reuse the current topology instead of rebuilding devices or links.
- Configure one device at a time.
- Prefer short CLI blocks pasted into the device `CLI` tab instead of many small interactive edits.
- Save the device config with `copy running-config startup-config`.
- After finishing a batch of device changes, return to the main Packet Tracer window and save the `.pkt` container itself with the toolbar Save button or `Cmd+S`.

## Important constraints discovered

- Saving a device startup-config is not enough. The outer `.pkt` file must also be saved from the main workspace window or changes may be lost.
- The current topology wiring in `deliverables/topologia.pkt` does not exactly match the written E1 description. Use the actual live links in the file unless the task explicitly requires rewiring.
- The current `.pkt` has networking devices only and no end hosts, so DHCP and end-to-end client validation cannot be fully proven without adding PCs.
- Core-switch CLI output can interleave with link-state messages while trunks come up. If a command entry is interrupted, re-enter the command in a clean block instead of assuming it applied.

## Practical recommendation

For future Packet Tracer work in this repo, make incremental changes, save often at both levels, and verify the final file timestamp on disk after closing the editing pass.
