<script lang="ts">
	// The ordering of these imports is critical to your app working properly
	import '@skeletonlabs/skeleton/themes/theme-skeleton.css';
	// If you have source.organizeImports set to true in VSCode, then it will auto change this ordering
	import '@skeletonlabs/skeleton/styles/all.css';
	// Most of your app wide CSS should be put in this file
	import '../app.postcss';
	import { AppShell, LightSwitch } from '@skeletonlabs/skeleton';
	import { ethers } from 'ethers'

let web3Wallet: any = null;

const requestAccount = async () => {
let signer = null;
let provider;
if (window.ethereum == null) {
    console.log("MetaMask not installed; using read-only defaults")
    provider = ethers.getDefaultProvider()
} else {
    provider = new ethers.BrowserProvider(window.ethereum)
    signer = await provider.getSigner();
	web3Wallet = signer.address.slice(0,5)+"..."+signer.address.slice(38)
}
}

</script>

<!-- App Shell -->
<!-- svelte-ignore a11y-click-events-have-key-events -->
<AppShell>
	<svelte:fragment slot="header">
		<div class="containter mx-auto">
			<div class="grid grid-cols-2 gap-4 items-center">
				<div class="grid-item-logo pl-16 pt-4">
					<a href="/" target="_self" rel="logo">
						<img src="../images/tokeneyeslabslogo.png" alt="" class="w-64" />
					</a>
				</div>

				<div class="grid-item-buttons flex justify-end space-x-4">
					<a class="btn btn-lg variant-ghost-surface" href="/about" target="_self" rel="noreferrer">
						About
					</a>

					<a
						class="btn btn-lg variant-ghost-surface"
						href="/markets"
						target="_self"
						rel="noreferrer"
					>
						Markets
					</a>

					<a
					class="btn btn-lg variant-ghost-surface"
					href="/contact"
					target="_self"
					rel="noreferrer"
				>
					Contact
				</a>

			
					<div on:click={()=> requestAccount()} class="btn btn-lg variant-ghost-surface">
						{
							web3Wallet === null ? "Connect" : web3Wallet
						}
					</div>
					<div class="grid justify-center items-center pr-8">
						<LightSwitch />
					</div>
				</div>
			</div>
		</div>
	</svelte:fragment>
	<!-- Page Route Content -->
	<slot />
</AppShell>
