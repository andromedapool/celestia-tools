<h1 align="center">CELESTIA TOOLS</h1>

<!-- TABLE OF CONTENTS -->
<h2 id="table-of-contents"> :book: Table of Contents</h2>

<details open="open">
  <summary>Table of Contents</summary>
  <ol>
    <li><a href="#about-the-project"> ➤ About the repo</a></li>
    <li><a href="#requirements"> ➤ Requirements</a></li>
    <li><a href="#deploy"> ➤ How to deploy your node</a></li>
    <li><a href="#contribute"> ➤ Contribute</a></li>
    <li><a href="#links"> ➤ Links</a></li>
  </ol>
</details>

![-----------------------------------------------------](assets/line.png)

<!-- ABOUT THE PROJECT -->
<h2 id="about-the-project"> :pencil: About The Project</h2>

<p align="justify"> 
  This GitHub repository provides an automated deployment process for setting up a <a href="https://docs.celestia.org/nodes/overview/">Celestia Node</a> using <a href="https://www.ansible.com/">Ansible</a>. In just 5 minutes, anyone can easily deploy their own Celestia Node on their preferred operating system.

Ansible is a powerful automation tool that allows users to write scripts to automate various system administration tasks. The deployment script included in this repository utilizes Ansible to automate the process of setting up a Celestia Node, including installing all necessary dependencies and configuring the node.

Moreover, the repository also includes a backup feature that helps users preserve their node's private keys, which are essential for participating in the Celestia network.

</p>

![-----------------------------------------------------](assets/line.png)

<!-- REQUIREMENTS -->
<h2 id="requirements"> :hammer: Requirements</h2>

- A server with <a href="https://docs.celestia.org/nodes/validator-node/#hardware-requirements">minim hardware requirements</a> -> We recommend Ubuntu >= 20.04 (LTS) x64
- Ansible installed on your local machine -> <a href="https://adamtheautomator.com/install-ansible/">How to install ansible on Ubuntu, RHEL, CentOS, macOS</a>
- sshpass package -> <a href="https://www.cyberciti.biz/faq/noninteractive-shell-script-ssh-password-provider/">How to install on linux</a> | `brew install esolitos/ipa/sshpass` for macOS
- That's it! :)

![-----------------------------------------------------](assets/line.png)

<!-- DEPLOY -->
<h2 id="deploy"> :book: How to deploy your node</h2>

<p>A) Clone this repository</p>
<pre><code>$ git clone https://github.com/andromedapool/celestia-tools</code></pre>

<p>B) Enter directory</p>
<pre><code>$ cd celestia-tools</code></pre>

<p>C) Adjust server configuration - edit `hosts` file</p>
<ol>
    <li><b>Set your remote server username:</b> ansible_user={your_server_user}</li> 
    <li><b>Set your remote server password:</b> ansible_ssh_pass={your_server_password} (NOTE: if you use ssh keys, then remove this line)</li> 
    <li><b>Set your remote server IP address:</b> ansible_host={your_server_ip_address}</li>
</ol>

<p>D) Adjust celestia node configuration - edit `roles/node/defaults/main.yml` file</p>

<ol>
    <li><b>Set celestia node type:</b> celestia_node_type: "{node_type}" (light/bridge/full) - <a href="https://docs.celestia.org/category/types-of-nodes/">Types of nodes</a></li>
    <li><b>Set celestia node version:</b> celestia_node_version: "{node_version}"  - <a href="https://github.com/celestiaorg/celestia-node/releases">Versions</a></li>
    <li><b>(OPTIONAL) Set keyring name:</b> celestia_keyring: "{you_wallet_name}"</li>
    <li><b>(OPTIONAL) Set RPC endpoint:</b> node_public_ip: "{ip_address or domain}" - <a href="https://docs.celestia.org/nodes/blockspace-race/#rpc-endpoints">List of RPC endpoints</a> or you cand use your own</li></li>

</ol>

<p>E) Deploy & start your node </p>
<pre><code>$ ansible-playbook -i hosts node.yml</code></pre>

<p>F) Backing up your mnemonic phrase </p>

- In the last step of the installation the mnemonic phrase will be shown. Put it in a safe place.

![-----------------------------------------------------](assets/line.png)

<!-- CONTRIBUTE -->
<h2 id="contribute"> :books: Contribute</h2>

- Contributions are welcomed, so feel free to fork/open pull requests.

![-----------------------------------------------------](assets/line.png)

<!-- LINKS -->
<h2 id="links"> :books: Links</h2>

- [Contact us on Twitter](https://twitter.com/andromedapool)
- [Reach us on Celestia Discord](https://discord.com/channels/638338779505229824)
- [Our Website](https://andromedapool.com/)
