# Fallback

You will beat this level if

1. you claim ownership of the contract
2. you reduce its balance to 0

# Solution

Ultimately, to drain the function we need to call the withdraw function, however only the owner can call this, therefore we need to become the owner

The receive function makes you the owner, therefore you need to trigger this function. However you can only trigger it if you are a contributor. So contribute first with

Await contract.contribute({value: 10e12})

Then send ether to contract (only need msg.value greater than 1, so here 1 Wei)

Await contract.sendTransaction({value: 1})

Finally, we can withdraw all the funds with

Await contract.withdraw()
