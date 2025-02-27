## 类型

此处引用了 SDK 中使用的所有类型：

```typescript
import { BytesLike, BigNumberish, providers, BigNumber } from 'ethers';

// 0x-prefixed, hex encoded, ethereum account address
export type Address = string;
// 0x-prefixed, hex encoded, ECDSA signature.
export type Signature = string;

// Ethereum network
export enum Network {
    Mainnet = 1,
    Ropsten = 3,
    Rinkeby = 4,
    Goerli = 5,
    Localhost = 9
}

export enum TransactionStatus {
    NotFound = 'not-found',
    Processing = 'processing',
    Committed = 'committed',
    Finalized = 'finalized'
}

export type PaymasterParams = {
    paymaster: Address;
    paymasterInput: BytesLike;
};

export type Eip712Meta = {
    ergsPerPubdata?: BigNumberish;
    factoryDeps?: BytesLike[];
    customSignature?: BytesLike;
    paymasterParams?: PaymasterParams;
};

// prettier-ignore
export type BlockTag =
    | number
    | string // hex number
    | 'committed'
    | 'finalized'
    | 'latest'
    | 'earliest'
    | 'pending';

export type DeploymentType = 'create' | 'createAccount';

export interface Token {
    l1Address: Address;
    l2Address: Address;
    /** @deprecated This field is here for backward compatibility - please use l2Address field instead */
    address: Address;
    name: string;
    symbol: string;
    decimals: number;
}

export interface MessageProof {
    id: number;
    proof: string[];
    root: string;
}

export interface EventFilter {
    topics?: Array<string | Array<string> | null>;
    address?: Address | Array<Address>;
    limit?: number;
    fromBlock?: BlockTag;
    toBlock?: BlockTag;
    blockHash?: string;
}

export interface TransactionResponse extends providers.TransactionResponse {
    waitFinalize(): Promise<providers.TransactionReceipt>;
}

export type TransactionRequest = providers.TransactionRequest & { customData?: Eip712Meta };

export interface PriorityOpResponse extends TransactionResponse {
    waitL1Commit(confirmation?: number): Promise<providers.TransactionReceipt>;
}

export type BalancesMap = { [key: string]: BigNumber };

export interface DeploymentInfo {
    sender: Address;
    bytecodeHash: string;
    deployedAddress: Address;
}

export interface ApprovalBasedPaymasterInput {
    type: 'ApprovalBased';
    token: Address;
    minimalAllowance: BigNumber;
    innerInput: BytesLike;
}

export interface GeneralPaymasterInput {
    type: 'General';
    innerInput: BytesLike;
}

export type PaymasterInput = ApprovalBasedPaymasterInput | GeneralPaymasterInput;
```
