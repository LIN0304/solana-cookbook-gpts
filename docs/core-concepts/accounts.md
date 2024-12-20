# Understanding Solana Accounts

## What are Accounts?

In Solana, accounts serve as storage units that hold data and SOL tokens. They are fundamental building blocks of the Solana ecosystem.

## Account Properties

- Owner: Program that has write authority
- Lamports: Amount of SOL held
- Data: Account data stored as bytes
- Executable: Boolean indicating if account contains program
- Rent Epoch: Next epoch when rent is due

## Account Types

1. System Owned Accounts
   - User wallets
   - General purpose storage

2. Program Owned Accounts (PDA)
   - Derived from programs
   - Cannot sign transactions
   - Deterministic addresses

3. Native Program Accounts
   - System Program
   - Token Program
   - Other native programs

## Best Practices

- Always verify account ownership
- Check for required signatures
- Handle rent correctly
- Use PDAs appropriately

## Code Examples

```typescript
// Create a new account
const newAccount = Keypair.generate();

// Create account instruction
const createAccountInstruction = SystemProgram.createAccount({
  fromPubkey: payer.publicKey,
  newAccountPubkey: newAccount.publicKey,
  lamports: rentExemptionAmount,
  space: dataSize,
  programId: programId,
});
```
