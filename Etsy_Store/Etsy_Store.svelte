<script>
import { s3__etsy_listing_a__, s3__etsy_listing_image_a__ } from '@ctx-core/etsy_cache'
export let ctx
const s3__etsy_listing_a_ = s3__etsy_listing_a__(ctx)
const s3__etsy_listing_image_a__new = s3__etsy_listing_image_a__(ctx)
</script>

<div class="Etsy_Store">
	{#each $s3__etsy_listing_a_||[] as s3_etsy_listing, i}
		<div class="listing" title="{s3_etsy_listing.description}">
			<div class="img-container">
				{#if $s3__etsy_listing_image_a_[i].url_75x75}
					<img
						src="{$s3__etsy_listing_image_a_[i].url_75x75}"
						alt="{s3_etsy_listing.description}"
					>
				{/if}
			</div>
			<div class="title">{@html s3_etsy_listing.title}</div>
			<div class="price">{s3_etsy_listing.price}</div>
			<a href={s3_etsy_listing.url} class="buy" target="_blank">Buy on Etsy</a>
		</div>
	{/each}
</div>

