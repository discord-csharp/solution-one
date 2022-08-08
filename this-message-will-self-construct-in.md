# This Message Will Self-Construct In...

## Description

Building an emergency plan is more than having a bug-out bag ready to go, it needs to include contingencies in the event you may not be there. Preparing for this by giving trusted individuals passwords or encryption keys may put them in danger too, so how can we solve this? Enter Timelock puzzles, and BouncyCastle.NET to make this tricky cryptographic process dead simple.

## Outline

- Setting the Stage
  - Brief example demonstrating the problem: dangerous information, dangerous people who want it.
  - Answer: What if there were a way you could make decryption only possible after a certain amount of time, giving you an opportunity to subvert the danger of knowledge?
- Plan of Attack: Timelock Cryptography
  - Simple demonstration of repeated squarings
  - Explanation on how this maps into a simple symmetric (AES) cryptography setting.
- Implementation: Basic encryption setup
  - How to use BouncyCastle to create a key and encrypt a file.
- Implementation: How to do the Timelock puzzle
  - Augmenting our basic encryption setup to use timelock puzzles
- Extra: Optional disclosure
  - Augmenting our timelock setup to allow passing a key to a trusted individual so they can decrypt quickly amongst others who must wait.
- Final notes/observations, close out.