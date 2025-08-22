# Install Percona's build of ProxySQL 2.x.x binary tarball

If installing [_ProxySQL 2_ with a package manager](install-v2.md) is not an option in your environment, you can install from a binary tarball. The difference between versions is the available tar files or the command to extract the file.

Starting with [_ProxySQL 2.3.2-1.2_](release-notes-2.3.2-1.md), Percona no longer provides a tarball for CentOS 6.  
For more information, see [Spring Cleaning: Discontinuing RHEL 6/CentOS 6 (glibc2.12) and 32-bit Binary Builds of Percona Software](https://www.percona.com/blog/spring-cleaning-discontinuing-rhel-6-centos-6-glibc-2-12-and-32-bit-binary-builds-of-percona-software/)

The password-based file encryption requires OpenSSL 1.1.1, but Ubuntu 16.04 does not support this OpenSSL version.  
A special statically linked OpenSSL 1.1.1 binary is packaged with the executable to avoid conflicts with the system OpenSSL and any shared libraries. Each new release rebuilds the binary.

---

## Installation Steps

1. Go to [Download ProxySQL](https://www.percona.com/downloads/proxysql/) and select the `ProxySQL 2` product.

2. In the **Select Product Version** field, choose the desired version.

3. In the **Select Platform** field, select **Linux - Generic**.

4. Select the tar file appropriate for your system.

:::note tar files for ProxySQL 2.4.4 and higher

| Name | Description |
|------|-------------|
| `proxysql-2-<version>-Linux-x86_64.glibc2.23.xenial.tar.gz` | For Ubuntu 16.04 `xenial` only |
| `proxysql-2-<version>-Linux-x86_64.glibc2.17.tar.gz` | For every supported OS |
| `proxysql-2-<version>-Linux-x86_64.glibc2.27.tar.gz` | For every supported OS except `xenial`. For CentOS 7, install OpenSSL 1.1.1 if needed. |

:::

:::note tar files from ProxySQL 2.3.2-1.2 to 2.4.3

| Name | Description |
|------|-------------|
| `proxysql-2-<version>-Linux-x86_64.glibc2.23.xenial.tar.gz` | For Ubuntu 16.04 `xenial` only |

:::

:::note tar files from ProxySQL 2.0.15 to 2.3.2

| Name | Description |
|------|-------------|
| `proxysql-2.0.XX-Linux-x86_64.glibc2.12.tar.gz` | For every supported OS except `xenial`. For CentOS 7, install OpenSSL 1.1.1 if needed. |
| `proxysql-2.x.xx-Linux-x86_64.glibc2.17.tar.gz` | For every supported OS |
| `proxysql-2.0.XX-Linux-x86_64.glibc2.23.xenial.tar.gz` | For Ubuntu 16.04 `xenial` only |

:::

> 💡 See also: ProxySQL 2.0.15 and proxysql-admin

---

5. Navigate to the downloaded tar file.

6. Extract the files.

#### Extract ProxySQL 2.0.14 or higher

```bash
# Extract the files to the download destination directory
tar xzf proxysql-2.X.X-<PLATFORM-ARCHITECTURE>.tar.gz

# Change to the directory that contains the extracted files
cd proxysql-<VERSION>-Linux-<PLATFORM-ARCHITECTURE>
```

#### Extract ProxySQL 2.0.13 or lower

```bash
# Extract the files (assumes you are in the download destination directory)
tar xzf proxysql-<VERSION>-Linux-<PLATFORM-ARCHITECTURE>.tar.gz

# Change to the directory that contains the extracted files
cd proxysql-<VERSION>-Linux-<PLATFORM-ARCHITECTURE>
```

7. Create a directory to store ProxySQL data:

```bash
mkdir /home/user/data
```

8. In the configuration file, update the datadir value:

```bash
datadir="/home/user/data"
```

9. Set other configuration options, as needed.

---

## See also

- [ProxySQL 2.x and proxysql-admin utility](proxysql-admin-tool-v2-config.md)
