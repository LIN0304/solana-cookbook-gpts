# SPL Token Integration

## Overview

SPL Tokens are Solana's standard for fungible and non-fungible tokens.

## Token Creation

```typescript
// Create mint account
const mintAccount = await Token.createMint(
  connection,
  payer,
  mintAuthority.publicKey,
  freezeAuthority.publicKey,
  decimals,
  TOKEN_PROGRAM_ID
);

// Create token account
const tokenAccount = await mintAccount.createAccount(owner.publicKey);

// Mint tokens
await mintAccount.mintTo(
  tokenAccount,
  mintAuthority,
  [],
  amount
);
```

## Token Management

1. Transfer Tokens
2. Freeze/Thaw Accounts
3. Close Accounts
4. Manage Authorities

## Security Considerations

- Token validation
- Authority checks
- Decimal handling
