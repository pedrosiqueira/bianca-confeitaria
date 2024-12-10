<div class="container">
	<main>
		<div class=" text-center">
			<img class="d-block mx-auto" src="/logo.webp" alt="" width="120" />
			<h2>Confeitaria da Bia</h2>
			<p class="lead">
				Brownieria, cafés gelados e quentes especiais, croissant´s doces e salgados.
			</p>
		</div>
		<hr />
		<ul class="nav justify-content-center">
			<li class="nav-item">
				<a class="nav-link btn" aria-current="page" href="#">Active</a>
			</li>
			<li class="nav-item">
				<a class="nav-link" href="#">Link</a>
			</li>
			<li class="nav-item">
				<a class="nav-link" href="#">Link</a>
			</li>
			<li class="nav-item">
				<a class="nav-link disabled" aria-disabled="true">Disabled</a>
			</li>
		</ul>
		<hr />
		<div class="d-grid gap-1">
			<button
				class="btn btn-primary"
				type="button"
				data-bs-toggle="collapse"
				data-bs-target="#collapseExample"
				aria-expanded="false"
				aria-controls="collapseExample"
			>
				Bom bons
			</button>
		</div>
		<div class="collapse" id="collapseExample">
			<div class="row row-cols-1 row-cols-md-3 g-4">
				<div class="col">
          <a class="text-decoration-none" href=""  data-bs-toggle="modal" data-bs-target="#exampleModal">
            <div class="card mb-3" style="max-width: 540px;">
						<div class="row g-0">
							<div class="col-md-4">
								<img src="/bom bom.webp" class="img-fluid rounded-start" alt="..." />
							</div>
							<div class="col-md-8">
								<div class="card-body">
									<h5 class="card-title">Card title</h5>
									<p class="card-text">
										This is a wider card with supporting text below as a natural lead-in to
										additional content. This content is a little bit longer.
									</p>
									<p class="card-text">
										<small class="text-body-secondary">Last updated 3 mins ago</small>
									</p>
								</div>
							</div>
						</div>
					</div></a>
				</div>
				<div class="col">
					<div class="card mb-3" style="max-width: 540px;">
						<div class="row g-0">
							<div class="col-md-4">
								<img src="/bom bom.webp" class="img-fluid rounded-start" alt="..." />
							</div>
							<div class="col-md-8">
								<div class="card-body">
									<h5 class="card-title">Card title</h5>
									<p class="card-text">
										This is a wider card with supporting text below as a natural lead-in to
										additional content. This content is a little bit longer.
									</p>
									<p class="card-text">
										<small class="text-body-secondary">Last updated 3 mins ago</small>
									</p>
								</div>
							</div>
						</div>
					</div>
				</div>
			</div>
		</div>
	</main>
</div>


<!-- Modal -->
<div class="modal fade" id="exampleModal" tabindex="-1" aria-labelledby="exampleModalLabel" aria-hidden="true">
  <div class="modal-dialog modal-dialog-centered">
    <div class="modal-content">
      <div class="modal-header">
        <h1 class="modal-title fs-5" id="exampleModalLabel">Modal title</h1>
        <button type="button" class="btn-close" data-bs-dismiss="modal" aria-label="Close"></button>
      </div>
      <div class="modal-body">
        <div class="row">
          <div class="col"><img src="/bom bom.webp" alt=""></div>
          <div class="col">Bom bom recheado sabor uva</div>
        </div>
      </div>
      <div class="modal-footer">
        <button type="button" class="btn btn-secondary" data-bs-dismiss="modal">Close</button>
        <button type="button" class="btn btn-primary">Save changes</button>
      </div>
    </div>
  </div>
</div>
