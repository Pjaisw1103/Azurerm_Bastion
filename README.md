<h1 align="center">🚀 Terraform Azure Infrastructure Automation</h1>

<p align="center">
  <img src="https://cdn-icons-png.flaticon.com/512/873/873120.png" width="90" alt="Terraform Logo"/>
</p>

<p align="center">
  This repository automates the creation and management of <b>Azure Cloud Infrastructure</b> using <b>Terraform</b>.<br>
  It follows a <b>modular structure</b> for better reusability, scalability, and maintainability.
</p>

<hr>

<h2>📂 Project Structure</h2>

<pre>
.
├── Environment
│   ├── main.tf
│   └── provider.tf
│
└── Module
    ├── azurerm_bastion
    ├── azurerm_mssql_database
    ├── azurerm_mssql_server
    ├── azurerm_public_ip
    ├── azurerm_resource_group
    ├── azurerm_subnet
    ├── azurerm_virtual_machine
    └── azurerm_virtual_network
</pre>

<hr>

<h2>🧩 Module Description</h2>

<ul>
  <li><b>azurerm_resource_group</b> → Creates Azure Resource Group.</li>
  <li><b>azurerm_virtual_network</b> → Defines Virtual Network for resource communication.</li>
  <li><b>azurerm_subnet</b> → Creates Subnets inside the Virtual Network.</li>
  <li><b>azurerm_public_ip</b> → Allocates Public IP for external connectivity.</li>
  <li><b>azurerm_virtual_machine</b> → Deploys Azure Virtual Machine.</li>
  <li><b>azurerm_bastion</b> → Enables secure Bastion access to VMs.</li>
  <li><b>azurerm_mssql_server</b> → Creates MSSQL Server instance.</li>
  <li><b>azurerm_mssql_database</b> → Creates Database inside the SQL Server.</li>
</ul>

<hr>

<h2>⚙️ How to Use</h2>

<ol>
  <li>Clone the repository:
    <pre><code>git clone &lt;repo-url&gt;</code></pre>
  </li>
  <li>Navigate to the <code>Environment</code> folder:
    <pre><code>cd Environment</code></pre>
  </li>
  <li>Initialize Terraform:
    <pre><code>terraform init</code></pre>
  </li>
  <li>Preview the changes:
    <pre><code>terraform plan</code></pre>
  </li>
  <li>Apply configuration to create resources:
    <pre><code>terraform apply -auto-approve</code></pre>
  </li>
</ol>

<hr>

<h2>🧠 Key Concepts</h2>

<ul>
  <li><b>Modular Design</b> → Simplifies maintenance and enables reuse of components.</li>
  <li><b>State Management</b> → Tracks infrastructure changes securely.</li>
  <li><b>Idempotency</b> → Running the same code repeatedly results in consistent infrastructure.</li>
</ul>

<hr>

<h2>📜 Prerequisites</h2>

<ul>
  <li>Terraform v1.5 or later</li>
  <li>Azure CLI configured</li>
  <li>Valid Azure Subscription</li>
</ul>

<hr>

<h2>💡 Best Practices</h2>

<ul>
  <li>Use remote backend for Terraform state (e.g., Azure Storage Account).</li>
  <li>Follow naming conventions for Azure resources.</li>
  <li>Use variables and outputs effectively for dynamic configurations.</li>
</ul>

<hr>

<h2>🤝 Contribution</h2>

<p>
  Contributions are always welcome!<br>
  If you’d like to improve or extend this project, please fork the repo and submit a pull request.
</p>

<hr>

<h2>🛡️ License</h2>

<p>This project is licensed under the <b>MIT License</b>.</p>

<hr>

<p align="center">
  Made with ❤️ using <b>Terraform</b> and <b>Azure</b>.
</p>
