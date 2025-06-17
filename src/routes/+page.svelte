<script>
	import { catálogo } from '$lib/produtos.js';
	import { SvelteSet } from 'svelte/reactivity';

	let p = $state({ imagem: '', título: 'test', descrição: 'descrição' });
	let carrinho = $state(new SvelteSet());
</script>

<div class="div-background"></div>
<div class="container">
	<main>
		<div class=" text-center">
			<img class="d-block mx-auto" src="/logo.webp" alt="" width="120" />
			<h3>Delicora</h3>
			<p class="lead">Brownieria, cafés gelados e quentes especiais, croissant´s doces e salgados.</p>
		</div>
		<span class="badge text-bg-danger">Aberto</span>
		<button type="button" class="btn btn-outline-danger" disabled> Calcular entrega</button>
		<hr />
		<ul class="nav justify-content-center">
			<li class="nav-item">
				<a class="nav-link" href="https://maps.app.goo.gl/qA9zdHWhDMrTh9Qv9" target="_blank"><i class="bi bi-geo-alt-fill"></i> Rotas</a>
			</li>
			<li class="nav-item">
				<a class="nav-link" href="#"><i class="bi bi-share-fill"></i> Compartilhar</a>
			</li>
			<li class="nav-item">
				<a class="nav-link" href="https://www.instagram.com/biancatavarescordeiro/" target="_blank"><i class="bi bi-instagram"></i> Instagram</a>
			</li>
			<li class="nav-item">
				<a class="nav-link" href="https://api.whatsapp.com/send/?phone=556791918207&text&type=phone_number&app_absent=0" target="_blank"><i class="bi bi-whatsapp"></i> WhatsApp</a>
			</li>
		</ul>
		<hr />
		<div class="accordion" id="accordionExample">
			{#each catálogo as item}
				<div class="accordion-item">
					<h2 class="accordion-header">
						<button class="accordion-button collapsed" type="button" data-bs-toggle="collapse" data-bs-target="#{item.id}">{item.categoria} </button>
					</h2>
					<div id={item.id} class="accordion-collapse collapse" data-bs-parent="#accordionExample">
						<div class="accordion-body">
							<div class="row row-cols-1 row-cols-md-2 g-4">
								{#each item.produtos as produto}
									<div class="col">
										<a class="text-decoration-none" href="" data-bs-toggle="modal" data-bs-target="#exampleModal" onclick={() => (p = produto)}>
											<div class="card mb-3" style="max-width: 560px;">
												<div class="row g-0">
													<div class="col-md-4">
														<img src={produto.imagem} class="img-fluid rounded-start" alt="..." />
													</div>
													<div class="col-md-8">
														<div class="card-body">
															<h5 class="card-title">{produto.título}</h5>
															<p class="card-text">
																{produto.descrição}
															</p>
															<p class="card-text" style="color:#bf8454">
																R$ {#if produto.desconto}
																	{produto.desconto}
																	<s>{produto.preço}</s>
																{:else}
																	{produto.preço}
																{/if}
															</p>
														</div>
													</div>
												</div>
											</div></a
										>
									</div>
								{/each}
							</div>
						</div>
					</div>
				</div>
			{/each}
		</div>
		<div class="position-fixed bottom-0 end-0"><button class="btn btn-danger m-2" data-bs-toggle="modal" data-bs-target="#modalcarrinho">Carrinho ({carrinho.size})</button></div>
	</main>
</div>

<!-- Modal produto -->
<div class="modal fade" id="exampleModal" tabindex="-1" aria-labelledby="exampleModalLabel" aria-hidden="true">
	<div class="modal-dialog modal-dialog-centered modal-xl">
		<div class="modal-content">
			<div class="modal-header">
				<button type="button" class="btn-close" data-bs-dismiss="modal" aria-label="Close"></button>
			</div>
			<div class="modal-body">
				<div>
					<div class="mx-auto">
						<img src={p.imagem} alt={p.título} width="30%" />
					</div>
					<h5>{p.título}</h5>
					<div>{p.descrição}</div>
				</div>
			</div>
			<div class="modal-footer">
				<div class="btn-group" role="group" aria-label="Basic mixed styles example">
					<button
						type="button"
						class="btn btn-danger"
						onclick={() => {
							if (p.qtd > 0) p.qtd--;
						}}>-</button
					>
					<button class="btn btn-outline-danger">{p.qtd}</button>
					<button class="btn btn-danger" onclick={() => p.qtd++}>+</button>
				</div>
				<!-- Botão carrinho -->
				{#each catálogo as item}
					{#each item.produtos as produto}
						<button onclick={() => carrinho.add(p)} data-bs-dismiss="modal" class="btn btn-danger">
							Adicionar R$ {#if produto.desconto}
								{p.qtd * produto.desconto}
							{:else}
								{p.qtd * p.preço}
							{/if}
						</button>
					{/each}
				{/each}
			</div>
		</div>
	</div>
</div>

<!-- Modal carrinho  -->
<div id="modalcarrinho" class="modal" tabindex="-1">
	<div class="modal-dialog modal-dialog-centered">
		<div class="modal-content">
			<div class="modal-header">
				<h5 class="modal-title"><i class="bi bi-cart3"></i> Carrinho</h5>
				<button type="button" class="btn-close" data-bs-dismiss="modal" aria-label="Close"></button>
			</div>
			<div class="modal-body">
				<ul class="list-group list-group-flush">
					{#each carrinho as item}
						<li class="list-group-item">{item.qtd} x {item.título}</li>
					{/each}
				</ul>
			</div>
			<div class="modal-footer">
				<button type="button" class="btn btn-secondary" data-bs-dismiss="modal"><i class="bi bi-cart3"></i> Continuar comprando</button>
				<button type="button" class="btn btn-danger"><i class="bi bi-arrow-right"></i> Finalizar pedido</button>
			</div>
		</div>
	</div>
</div>

<style>
	.div-background {
		height: 150px;
		background-color: pink;
		border-bottom: 3px dashed #bf8454;
	}
</style>
