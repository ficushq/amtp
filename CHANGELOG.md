# Changelog

## 0.2.0 (2026-10-27)

- Sign authenticated GETs over proxy-stable AMTP route-relative paths.
- Accept one bounded legacy observed-path candidate during the transition.
- Add an outbound per-peer compatibility prefix for prefixed 0.1 receivers.
- Add local structured authentication diagnostics while preserving uniform 401 responses.
- Fix [#2](https://github.com/ficushq/amtp/issues/2).
- Accept zod 4: `amtp-protocol` now depends on `zod ^3.25.0 || ^4.0.0`, and all three packages build and test on both majors.
- Use the two-argument `z.record(z.string(), …)` form, which zod 4 requires.
- Type the exported schemas (`amtpEnvelopeSchema`, `amtpAttachmentRefSchema`, `amtpAgentCardSchema`, `amtpSignedAgentCardSchema`) as `z.ZodType<T>` so the published declarations typecheck under either zod major. Consumers that called `ZodObject`-only methods such as `.shape` or `.extend` on them must now build their own schemas.
