<script>
	import { catálogo } from '$lib/produtos.js';
</script>

<div class="div-background"></div>
<div class="container">
	<main>
		<div class=" text-center">
			<img class="d-block mx-auto" src="/logo.webp" alt="" width="120" />
			<h3>Delicora</h3>
			<p class="lead">
				Brownieria, cafés gelados e quentes especiais, croissant´s doces e salgados.
			</p>
		</div>
		<h5><span class="badge text-bg-danger">Aberto</span></h5>
		<button type="button" class="btn btn-outline-danger" disabled> Calcular entrega</button>
		<hr />
		<ul class="nav justify-content-center">
			<li class="nav-item">
				<a
					class="nav-link"
					href="https://maps.app.goo.gl/qA9zdHWhDMrTh9Qv9"
					target="_blank"><i class="bi bi-geo-alt-fill"></i> Rotas</a
				>
			</li>
			<li class="nav-item">
				<a class="nav-link" href="#"><i class="bi bi-share-fill"></i> Compartilhar</a>
			</li>
			<li class="nav-item">
				<a class="nav-link" href="https://www.instagram.com/biancatavarescordeiro/" target="_blank"
					><i class="bi bi-instagram"></i> Instagram</a
				>
			</li>
			<li class="nav-item">
				<a
					class="nav-link"
					href="https://api.whatsapp.com/send/?phone=556791918207&text&type=phone_number&app_absent=0"
					target="_blank"><i class="bi bi-whatsapp"></i> WhatsApp</a
				>
			</li>
		</ul>
		<hr />
		<div class="accordion" id="accordionExample">
			{#each catálogo as item}
				<div class="accordion-item">
					<h2 class="accordion-header">
						<button
							class="accordion-button collapsed"
							type="button"
							data-bs-toggle="collapse"
							data-bs-target="#{item.id}"
							>{item.categoria}
						</button>
					</h2>
					<div
						id={item.id}
						class="accordion-collapse collapse"
						data-bs-parent="#accordionExample"
					>
						<div class="accordion-body">
							<div class="row row-cols-1 row-cols-md-2 g-4">
								{#each item.produtos as produto}
									<div class="col">
										<a
											class="text-decoration-none"
											href=""
											data-bs-toggle="modal"
											data-bs-target="#exampleModal"
										>
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
															<p class="card-text" style="color:blueviolet">
																	{#if produto.desconto}
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
	</main>
</div>

<!-- Modal -->
<div
	class="modal fade"
	id="exampleModal"
	tabindex="-1"
	aria-labelledby="exampleModalLabel"
	aria-hidden="true"
>
	<div class="modal-dialog modal-dialog-centered modal-xl">
		<div class="modal-content">
			<div class="modal-header">
				<h1 class="modal-title fs-5" id="exampleModalLabel">Modal title</h1>
				<button type="button" class="btn-close" data-bs-dismiss="modal" aria-label="Close"></button>
			</div>
			<div class="modal-body">
				<div class="mx-auto"><img src="/bom bom.webp" alt="" width="50%" /></div>
				<div>Bom bom recheado sabor uva</div>
			</div>
			<div class="modal-footer">
				<button type="button" class="btn btn-secondary" data-bs-dismiss="modal">Close</button>
				<button type="button" class="btn btn-primary">Save changes</button>
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

	.btn {
		padding: 5px;
		position: relative;
		bottom: 39px;
		left: 80px;
	}
</style>
