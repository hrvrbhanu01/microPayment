# microPaymentChannel


This is a Solidity smart contract that implements a payment channel where the recipient pays the transaction fee. The contract is called "ReceiverPays" and it has the following features:

The contract is owned by the address that created it, which is recorded in the "owner" variable.
The contract has a constructor that accepts Ether and the "payable" keyword is used to indicate that the contract can receive payments.
The "claimPayment" function is the main function that users will interact with. It takes three arguments: "amount", "nonce", and "signature". "amount" is the amount of Ether being transferred, "nonce" is a unique identifier for the transaction, and "signature" is the signature of the message that was signed by the sender. The function checks that the "nonce" has not been used before and that the signature is valid using the "recoverSigner" and "prefixed" functions. If the checks pass, the function transfers the "amount" of Ether to the sender using the "transfer" function.
The "shutdown" function can be called by the owner of the contract to destroy the contract and reclaim any remaining funds.
The "splitSignature", "recoverSigner", and "prefixed" functions are internal functions used by the "claimPayment" function to validate the signature and message.
It is worth noting that this contract may generate a warning due to the use of the "selfdestruct" function, which has been deprecated in favor of the "transfer" function in newer versions of Solidity.
