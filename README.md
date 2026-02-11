# AiiDAlab – Teaching Environment 2026

## Access Requirements

Dear students,

To follow the exercises of the course, you will need a **GitHub account**.

Please create one here:

[https://github.com/signup](https://github.com/signup)

After creating your account, send us an email with your **GitHub username**.

Your GitHub credentials will be required to access the **cloud deployment of AiiDAlab**.

---

# Option A — Use the Cloud Deployment (Recommended)

No local installation is required.
You only need:

* A GitHub account
* A web browser (**Chrome highly recommended**)
* A stable internet connection

---

# Option B — Install AiiDAlab Locally

If you have:

* A recent Linux or macOS computer
* More than 16 GB RAM
* More than 50 GB free disk space
* A stable internet connection

you may install AiiDAlab on your own computer.

---

## Step 1 — Install Docker Desktop

Install the latest version of Docker Desktop:

[https://docs.docker.com/desktop/setup/install/mac-install/](https://docs.docker.com/desktop/setup/install/mac-install/)

Make sure **Docker Desktop is running** before proceeding.
<img width="1085" height="439" alt="image" src="https://github.com/user-attachments/assets/c168b2df-d7f5-4afb-acc8-61abc922c7e7" />


 In the container settings (gear icon in the top right), configure the resources **before running AiiDAlab for the first time**.
 Set:

 * At least **2 CPUs** (do not allocate more than half of the available cores)
 * At least **16 GB of RAM** (do not allocate all available memory)
 * At least **50 GB of disk space** (do not allocate all available storage)

<img width="793" height="570" alt="image" src="https://github.com/user-attachments/assets/752415b4-3206-4428-a48f-9a5156dc3225" />

---

## Step 2 — Install aiidalab-launch

Open a terminal and run:

```bash
pip install aiidalab-launch
```

Project repository:

[https://github.com/aiidalab/aiidalab-launch](https://github.com/aiidalab/aiidalab-launch)

---

## Step 3 — Create a Profile

Create a new profile:

```bash
aiidalab-launch profile add teaching2026
```

When prompted whether you want to edit the profile, reply:

```
Y
```

You will see something similar to:

```toml
port = 8917
default_apps = []
system_user = "jovyan"
image = "docker.io/aiidalab/full-stack:latest"
home_mount = "aiidalab_teaching2026_home"
extra_mounts = []
```

Modify only the `image` line.

Replace:

```toml
image = "docker.io/aiidalab/full-stack:latest"
```

with:

```toml
image = "ghcr.io/nanotech-empa/aiidalab-for-teaching:main"
```


Save and exit the editor (typically `vi`).

---

## Step 4 — Start AiiDAlab

The Docker images will be available starting **February 13th**.

Start AiiDAlab with:

```bash
aiidalab-launch start --profile teaching2026
```
This may take several minutes, depending on your internet connection. If the connection is slow, you might need to rerun the command if a timeout error occurs.

When asked whether to open the web browser, reply:

```
Y
```
<img width="580" height="199" alt="image" src="https://github.com/user-attachments/assets/56548b2e-ac13-49b0-b59a-ce5dd688537d" />

<img width="946" height="224" alt="image" src="https://github.com/user-attachments/assets/ddd3b854-8d97-44c1-b4aa-2abbe6717cd9" />


If you check Docker desktop you will see a running container

<img width="1083" height="426" alt="image" src="https://github.com/user-attachments/assets/a42cd3c4-09d7-49c0-bbee-386fda24e578" />

---

## Step 5 — Stop AiiDAlab

To stop AiiDAlab, in a terminal of your PC run:

```bash
aiidalab-launch stop --profile teaching2026
```
<img width="578" height="55" alt="image" src="https://github.com/user-attachments/assets/87a8ca8a-921f-41f7-94ed-ae967169e171" />
