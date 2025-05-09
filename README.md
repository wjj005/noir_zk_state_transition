# Noir ZK State Transition Proof (Simplified MACI-like Message)

This project, inspired by concepts like MACI (Minimal Anti-Collusion Infrastructure), demonstrates a simplified Zero-Knowledge proof for verifying a state transition (e.g., a user updating their registered key) using the Noir language. It's designed for educational purposes like NoirHack to illustrate how ZK proofs can validate the integrity of state changes processed by a potentially untrusted coordinator or allow users to prove the validity of their own state-modifying messages, all while preserving privacy.

## Core Concept

In systems like MACI, users often submit encrypted messages to a coordinator to perform actions such as registering a public key, changing it, or casting a vote. This ZK circuit focuses on proving the validity of such a state transition message itself.

The prover (either a user constructing a message or a coordinator processing it) demonstrates that:
1.  They are associated with a known public identity commitment.
2.  If updating an existing state, they had knowledge of the secrets that formed the commitment to the previous state.
3.  The new state (e.g., containing a new public key and a message nonce) is correctly committed to.

This entire process occurs without revealing the actual identity secret, old/new key details, or message contents directly to verifiers, only their cryptographic commitments.

## Project Structure