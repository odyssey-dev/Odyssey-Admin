<header class="navbar navbar-header navbar-header-fixed">
	<span  id="mainMenuOpen" class="burger-menu d-none"><i data-feather="menu"></i></span>
	<span id="filemgrMenu" class="burger-menu d-lg-none"><i data-feather="arrow-left"></i></span>
	<div class="navbar-brand">
		<a href="/index.html" class="df-logo">Odyssey<span>Admin</span></a>
	</div>
	<div id="navbarMenu" class="navbar-menu-wrapper">
		<div class="navbar-menu-header">
			<a href="/index.html" class="df-logo">Odyssey<span>Admin</span></a>
			<a id="mainMenuClose" href=""><i data-feather="x"></i></a>
		</div>
	</div>
	{#if userState == true }
	<div class="navbar-right">
		<div class="dropdown dropdown-profile">
			<a href="#" class="dropdown-link" data-toggle="dropdown" data-display="static">
				<div class="avatar avatar-sm"><img src="" class="rounded-circle" alt=""></div>
			</a>
			<div class="dropdown-menu dropdown-menu-right tx-13">

				<h6 class="tx-semibold mg-b-5"> {username}</h6>
				<p class="mg-b-25 tx-12 tx-color-03">Administrator</p>
				<div class="dropdown-item" on:click={logout} ><i data-feather="log-out"></i>Sign Out</div>
			</div>
		</div>
	</div>
	{/if}
</header>


{#if userState == true }
	<div class="filemgr-wrapper">
		<div class="filemgr-sidebar">
			<div class="filemgr-sidebar-header">
				<div class="dropdown dropdown-icon flex-fill mg-l-10">
					<button class="btn btn-xs btn-block btn-primary" data-toggle="dropdown">New Badges</button>
				</div>
			</div>
			<div class="filemgr-sidebar-body">
				<div class="pd-t-20 pd-b-10 pd-x-10">
					<nav class="nav nav-sidebar tx-13">
						<a href="#" class="nav-link active"><i data-feather="map"></i> <span>All Badges</span></a>
						<a href="#" class="nav-link"><i data-feather="award"></i> <span>Continents</span></a>
						<a href="#" class="nav-link"><i data-feather="globe"></i> <span>Country</span></a>
						<a href="#" class="nav-link"><i data-feather="map-pin"></i> <span>Counties</span></a>
						<a href="#" class="nav-link"><i data-feather="map-pin"></i> <span>Citys & Towns </span></a>
						<a href="#" class="nav-link"><i data-feather="target"></i> <span>Attractions</span></a>
						<a href="#" class="nav-link"><i data-feather="calendar"></i> <span>Calendar</span></a>
					</nav>
				</div>
			</div>
		</div>
	
		<div class="filemgr-content">
			<div class="filemgr-content-header">
				<i data-feather="search"></i>
				<div class="search-form">
					<input type="search" class="form-control" placeholder="Search for Badges">
				</div>
				<nav class="nav d-none d-sm-flex mg-l-auto">
					<a href="#" class="nav-link"><i data-feather="list"></i></a>
				</nav>
			</div>
			<div class="filemgr-content-body">
				<div class="pd-20 pd-lg-25 pd-xl-30">
					<h4 class="mg-b-15 mg-lg-b-25">All Badges</h4>

					<hr class="mg-y-40 bd-0">
					<label class="d-block tx-medium tx-10 tx-uppercase tx-sans tx-spacing-1 tx-color-03 mg-b-15">Country</label>
					<div class="row row-xs">
						{#each badges as badge}
							<div class="col-6 col-sm-4 col-md-3">
								<div class="card card-file">
									<div class="dropdown-file">
										<a href="#" class="dropdown-link" data-toggle="dropdown"><i data-feather="more-vertical"></i></a>
										<div class="dropdown-menu dropdown-menu-right">
											<a href="#modalViewDetails" data-toggle="modal" class="dropdown-item details"><i data-feather="info"></i>View Details</a>
											<a href="#" class="dropdown-item important"><i data-feather="star"></i>Mark as Important</a>
											<a href="#modalShare" data-toggle="modal" class="dropdown-item share"><i data-feather="share"></i>Share</a>
											<a href="#" class="dropdown-item download"><i data-feather="download"></i>Download</a>
											<a href="#modalCopy" data-toggle="modal" class="dropdown-item copy"><i data-feather="copy"></i>Copy to</a>
											<a href="#modalMove" data-toggle="modal" class="dropdown-item move"><i data-feather="folder"></i>Move to</a>
											<a href="#" class="dropdown-item rename"><i data-feather="edit"></i>Rename</a>
											<a href="#" class="dropdown-item delete"><i data-feather="trash"></i>Delete</a>
										</div>
									</div>
									<div class="card-file-thumb tx-primary">
										<img src="assets/badge.svg" width="60px">
									</div>
									<div class="card-body">
										<h6><a href="#" class="link-02">{badge.name}</a></h6>
										<p>{badge.type}</p>
										<span>{badge.points}</span>
									</div>
								</div>
							</div>
						{/each}
					
						
					</div>
				</div>
			</div>
		</div>

	</div>

	<div class="modal fade effect-scale" id="modalViewDetails" tabindex="-1" role="dialog" aria-hidden="true">
		<div class="modal-dialog modal-dialog-centered" role="document">
			<div class="modal-content">
				<div class="modal-body pd-20 pd-sm-30">
					<button type="button" class="close pos-absolute t-15 r-20" data-dismiss="modal" aria-label="Close">
						<span aria-hidden="true">&times;</span>
					</button>

					<h5 class="tx-18 tx-sm-20 mg-b-30">View Details</h5>

					<div class="row mg-b-10">
						<div class="col-4">Filename:</div>
						<div class="col-8">Medical Certificate.pdf</div>
					</div>
					<div class="row mg-b-10">
						<div class="col-4">File ype:</div>
						<div class="col-8">PDF File</div>
					</div>
					<div class="row mg-b-10">
						<div class="col-4">File Size:</div>
						<div class="col-8">10.45 KB</div>
					</div>
					<div class="row mg-b-10">
						<div class="col-4">Created:</div>
						<div class="col-8">Monday, July 02, 2018 9:34am</div>
					</div>
					<div class="row mg-b-10">
						<div class="col-4">Modified:</div>
						<div class="col-8">Monday, July 02, 2018 9:34am</div>
					</div>
					<div class="row mg-b-10">
						<div class="col-4">Accessed:</div>
						<div class="col-8">Monday, July 02, 2018 9:34am</div>
					</div>
					<div class="row mg-b-10">
						<div class="col-4">Description:</div>
						<div class="col-8">
							<textarea class="form-control mg-t-5" rows="2" placeholder="Add description"></textarea>
						</div>
					</div>

				</div>
				<div class="modal-footer">
					<button type="button" class="btn btn-secondary mg-sm-l-5" data-dismiss="modal">Close</button>
				</div>
			</div>
		</div>
	</div>

	<div class="modal fade effect-scale" id="modalShare" tabindex="-1" role="dialog" aria-hidden="true">
		<div class="modal-dialog modal-dialog-centered" role="document">
			<div class="modal-content">
				<div class="modal-body pd-20 pd-sm-30">
					<button type="button" class="close pos-absolute t-15 r-20" data-dismiss="modal" aria-label="Close">
						<span aria-hidden="true">&times;</span>
					</button>

					<h5 class="tx-18 tx-sm-20 mg-b-30">Share With Others</h5>

					<div class="mg-t-20">
						<label class="d-block">Other users:</label>
						<input class="form-control" placeholder="Enter names or email addresses">
						<div class="dropdown mg-t-10">
							Rights: <a href="#" class="dropdown-link" data-toggle="dropdown">Allow editing <i class="icon ion-chevron-down tx-12"></i></a>
						</div>
						<hr>
						<label class="d-block">More:</label>
						<nav class="nav nav-social">
							<a href="#" class="nav-link"><i data-feather="facebook"></i></a>
							<a href="#" class="nav-link"><i data-feather="twitter"></i></a>
						</nav>
					</div>
				</div>
				<div class="modal-footer">
					<button type="button" class="btn btn-primary">Share</button>
				</div>
			</div>
		</div>
	</div>

	<div class="modal fade effect-scale" id="modalCopy" tabindex="-1" role="dialog" aria-hidden="true">
		<div class="modal-dialog modal-dialog-centered" role="document">
			<div class="modal-content">
				<div class="modal-body pd-20 pd-sm-30">
					<button type="button" class="close pos-absolute t-15 r-20" data-dismiss="modal" aria-label="Close">
						<span aria-hidden="true">&times;</span>
					</button>

					<h5 class="tx-18 tx-sm-20 mg-b-0">Copy Item to</h5>
					<p class="mg-b-25 tx-color-03">Please select a folder</p>

					<div class="bd bg-ui-01 pd-10">
						<ul class="nav nav-sidebar flex-column tx-13">
							<li class="nav-item"><a href="#" class="nav-link"><i data-feather="folder"></i> Downloads</a></li>
							<li class="nav-item"><a href="#" class="nav-link"><i data-feather="folder"></i> Personal Stuff</a></li>
							<li class="nav-item"><a href="#" class="nav-link"><i data-feather="folder"></i> 3d Objects</a></li>
							<li class="nav-item"><a href="#" class="nav-link"><i data-feather="folder"></i> Recordings</a></li>
							<li class="nav-item"><a href="#" class="nav-link"><i data-feather="folder"></i> Support</a></li>
						</ul>
					</div>
				</div>
				<div class="modal-footer">
					<button type="button" class="btn btn-secondary mg-sm-r-5" data-dismiss="modal">Close</button>
					<button type="button" class="btn btn-primary">Copy</button>
				</div>
			</div>
		</div>
	</div>

	<div class="modal fade effect-scale" id="modalMove" tabindex="-1" role="dialog" aria-hidden="true">
		<div class="modal-dialog modal-dialog-centered" role="document">
			<div class="modal-content">
				<div class="modal-body pd-20 pd-sm-30">
					<button type="button" class="close pos-absolute t-15 r-20" data-dismiss="modal" aria-label="Close">
						<span aria-hidden="true">&times;</span>
					</button>

					<h5 class="tx-18 tx-sm-20 mg-b-0">Move Item to</h5>
					<p class="mg-b-25 tx-color-03">Please select a folder</p>

					<div class="bd bg-ui-01 pd-10">
						<ul class="nav nav-sidebar flex-column tx-13">
							<li class="nav-item"><a href="#" class="nav-link"><i data-feather="folder"></i> Downloads</a></li>
							<li class="nav-item"><a href="#" class="nav-link"><i data-feather="folder"></i> Personal Stuff</a></li>
							<li class="nav-item"><a href="#" class="nav-link"><i data-feather="folder"></i> 3d Objects</a></li>
							<li class="nav-item"><a href="#" class="nav-link"><i data-feather="folder"></i> Recordings</a></li>
							<li class="nav-item"><a href="#" class="nav-link"><i data-feather="folder"></i> Support</a></li>
						</ul>
					</div>
				</div>
				<div class="modal-footer">
					<button type="button" class="btn btn-secondary mg-sm-r-5" data-dismiss="modal">Close</button>
					<button type="button" class="btn btn-primary">Move</button>
				</div>
			</div>
		</div>
	</div>

	<div class="pos-fixed b-10 r-10">
		<div id="toast" class="toast bg-dark bd-0 wd-300" data-delay="3000" role="alert" aria-live="assertive" aria-atomic="true">
			<div class="toast-header bg-transparent bd-white-1">
				<h6 class="tx-white mg-b-0 mg-r-auto">Downloading</h6>
				<button type="button" class="ml-2 mb-1 close tx-normal tx-shadow-none" data-dismiss="toast" aria-label="Close">
					<span aria-hidden="true">&times;</span>
				</button>
			</div>
			<div class="toast-body pd-10 tx-white">
				<h6 class="mg-b-0">Medical_Certificate.pdf</h6>
				<span class="tx-color-03 tx-11">1.2mb of 4.5mb</span>
				<div class="progress ht-5 mg-t-5">
					<div class="progress-bar wd-50p" role="progressbar" aria-valuenow="25" aria-valuemin="0" aria-valuemax="100"></div>
				</div>
			</div>
		</div>
	</div>

{:else if userState == false}
	<div class="content content-fixed content-auth">
		<div class="container">
			<div class="media align-items-stretch justify-content-center ht-100p pos-relative">

				<div class="sign-wrapper wd-400">
					<div class="wd-100p">
						<h3 class="tx-color-01 mg-b-5">Sign In</h3>
						<p class="tx-color-03 tx-16 mg-b-40">Please signin to continue.</p>

						<div class="form-group">
							<label>Email address</label>
							<input type="email" class="form-control" placeholder="yourname@yourmail.com" bind:value={email}>
						</div>
						<div class="form-group">
							<div class="d-flex justify-content-between mg-b-5">
								<label class="mg-b-0-f">Password</label>
								<!-- <a href="" class="tx-13">Forgot password?</a> -->
							</div>
							<input type="password" class="form-control" placeholder="Enter your password" bind:value={password}>
						</div>
						<button class="btn btn-brand-02 btn-block" on:click={() => signin(email, password)} >Sign In</button>
						<!-- <div class="divider-text">or</div>
						<button class="btn btn-outline-facebook btn-block">Sign In With Facebook</button>
						<button class="btn btn-outline-twitter btn-block">Sign In With Twitter</button>
						<div class="tx-13 mg-t-20 tx-center">Don't have an account? <a href="page-signup.html">Create an Account</a></div> -->
					</div>
				</div>
			</div>
		</div>
	</div>
{:else}
  <img class="loading" src="assets/svg/loading.svg" alt="loading" width="50" height="50">
{/if}


<style>
  .loading {
    position: absolute;
    top: 50%;
    width: 100%;
    margin: 0 auto;
  }
</style>

<script>
// Your web app's Firebase configuration
  // For Firebase JS SDK v7.20.0 and later, measurementId is optional
	var firebaseConfig = {
		apiKey: "AIzaSyCAuc2ZqdRMrkP5bHjrwR3CenWm4kdy7Lg",
		authDomain: "odyssey-admin.firebaseapp.com",
		databaseURL: "https://odyssey-admin.firebaseio.com",
		projectId: "odyssey-admin",
		storageBucket: "odyssey-admin.appspot.com",
		messagingSenderId: "346799321140",
		appId: "1:346799321140:web:838932d479647f17bada61",
		measurementId: "G-5DX8QKZPMQ"
	};
// Initialize Firebase
firebase.initializeApp(firebaseConfig);
firebase.analytics();

const auth = firebase.auth();

function login(email, password) {
	auth.signInWithEmailAndPassword(email, password).catch(function(error) {
		// Handle Errors here.
		var errorCode = error.code;
		var errorMessage = error.message;
		// ...
	});
}

function logout() {
  auth.signOut().then(function() {
  // Sign-out successful.
	}).catch(function(error) {
		// An error happened.
	});
}

	var userState;
	var username;
	auth.onAuthStateChanged(user => {
		if (user){
			username = user.email;
			userState = true;
		} else {
			userState = false;
		}
	});

	var email = "";
	var password = "";

	function signin(email, password) {
		login(email, password);
	}

	var badges = [
		{ id: 1, name: 'Badge Name', type: 'Country', points: '10' },
		{ id: 2, name: 'Badge Name', type: 'Country', points: '10' },
		{ id: 3, name: 'Badge Name', type: 'Country', points: '10' },
		{ id: 4, name: 'Badge Name', type: 'Country', points: '10' },
		{ id: 5, name: 'Badge Name', type: 'Country', points: '10' },
		{ id: 6, name: 'Badge Name', type: 'Country', points: '10' },
		{ id: 7, name: 'Badge Name', type: 'Country', points: '10' },
		{ id: 8, name: 'Badge Name', type: 'Country', points: '10' }
	];

</script>

