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
  <li><b>azurerm_resource_group</b> → Creates Azure Resource Group to hold all resources.</li>
  <li><b>azurerm_virtual_network</b> → Defines Virtual Network for internal resource communication.</li>
  <li><b>azurerm_subnet</b> → Creates Subnets inside the Virtual Network.</li>
  <li><b>azurerm_public_ip</b> → Allocates Public IP for external connectivity.</li>
  <li><b>azurerm_virtual_machine</b> → Deploys Azure Virtual Machine for workloads.</li>
  <li><b>azurerm_bastion</b> → Deploys an Azure Bastion Host that provides secure RDP/SSH access to Virtual Machines directly through the Azure Portal, without exposing any public IPs.</li>
  <li><b>azurerm_mssql_server</b> → Creates MSSQL Server instance to host databases.</li>
  <li><b>azurerm_mssql_database</b> → Creates Database inside the SQL Server for application data.</li>
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
  <li>Preview the planned changes:
    <pre><code>terraform plan</code></pre>
  </li>
  <li>Apply the configuration to create Azure resources:
    <pre><code>terraform apply -auto-approve</code></pre>
  </li>
</ol>

<hr>

<h2>🧠 Key Concepts</h2>

<ul>
  <li><b>Modular Design</b> → Each component is isolated as a module for reuse and maintainability.</li>
  <li><b>State Management</b> → Terraform keeps track of deployed resources through state files.</li>
  <li><b>Idempotency</b> → Re-running configurations ensures consistent infrastructure deployment.</li>
</ul>

<hr>

<h2>🛡️ Azure Bastion Overview</h2>

<p>
  The <b>Azure Bastion</b> service allows you to securely connect to your virtual machines over SSL directly from the Azure portal without the need for a public IP address on the VM.<br><br>
  <b>Key Benefits:</b>
</p>

<ul>
  <li>No public IP exposure on Virtual Machines.</li>
  <li>Secure RDP and SSH connectivity through Azure portal.</li>
  <li>Managed service by Microsoft, reducing maintenance overhead.</li>
  <li>Seamless access from browsers with enhanced security.</li>
</ul>

<hr>

<h2>📜 Prerequisites</h2>

<ul>
  <li>Terraform v1.5 or later</li>
  <li>Azure CLI installed and logged in</li>
  <li>Valid Azure Subscription</li>
</ul>

<hr>

<h2>💡 Best Practices</h2>

<ul>
  <li>Use remote backend (e.g., Azure Storage Account) for Terraform state files.</li>
  <li>Follow consistent naming conventions for Azure resources.</li>
  <li>Define input variables and outputs for modularity and dynamic configurations.</li>
  <li>Use tags for cost management and organization.</li>
</ul>

<hr>

<h2>🤝 Contribution</h2>

<p>
  Contributions are always welcome!<br>
  If you’d like to improve or extend this project, please fork the repository and submit a pull request.
</p>

<hr>

<p align="center">
  Made with ❤️ using <b>Terraform</b> and <b>Microsoft Azure</b>.<br>
  <i>Automate • Deploy • Scale</i>
</p>
