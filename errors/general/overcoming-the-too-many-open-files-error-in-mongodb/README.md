# 🐞 Overcoming the "Too Many Open Files" Error in MongoDB


## Description of the Error

The "Too many open files" error in MongoDB arises when the MongoDB process exceeds the operating system's limit on the number of simultaneously open files. This typically manifests as MongoDB failing to start, or existing connections being abruptly dropped with errors indicating file handle exhaustion. This is a common issue, especially on systems with many concurrent connections or those running resource-intensive applications alongside MongoDB.


## Steps to Fix the Issue

The solution involves increasing the operating system's maximum number of open files allowed for the MongoDB process. The specific steps depend on your operating system. Below are examples for Linux (using systemd) and macOS.  **Always back up your data before making system-level changes.**


### Linux (using systemd)

1. **Identify the current limit:**

   ```bash
   ulimit -n
   ```

   This command shows your current soft and hard limits for open files.

2. **Increase the limits (temporarily for the current session):**

   ```bash
   ulimit -n 65536  # Set the soft and hard limits to 65536 (adjust as needed)
   ```

3. **Permanently increase the limits:**

   Edit your systemd unit file for MongoDB.  The path might vary slightly depending on your distribution, but it's often located at `/etc/systemd/system/mongod.service`.  Add or modify the following lines within the `[Service]` section:

   ```ini
   [Service]
   LimitNOFILE=65536
   LimitNPROC=65536 # Consider increasing this as well if you expect many processes
   ```

4. **Reload systemd and restart MongoDB:**

   ```bash
   sudo systemctl daemon-reload
   sudo systemctl restart mongod
   ```

5. **Verify the change:**

   Check the MongoDB logs (`mongod.log`) to ensure it started successfully and that the file limit is correctly applied.  Also run `ulimit -n` within a new shell to confirm the change has taken effect on a new process.


### macOS

1. **Identify the current limit:**

   ```bash
   ulimit -n
   ```

2. **Increase the limit (temporarily for the current session):**

   ```bash
   ulimit -n 65536 # Set the soft and hard limits to 65536 (adjust as needed)
   ```

3. **Permanently increase the limits:**

   Edit the `limits.conf` file located at `/etc/launchd.conf`. Add the following line (adjust the number as needed, replacing "mongod" with the actual username the MongoDB process runs under):

   ```
   mongod hard nofile 65536
   mongod soft nofile 65536
   ```

4. **Restart your system or the MongoDB process:**  This ensures the changes take effect.

5. **Verify the change:** Check MongoDB logs and the output of `ulimit -n` after restarting.

## Explanation

The operating system limits the number of open files a process can have to prevent resource exhaustion.  When MongoDB handles many connections, or if there's a high level of file I/O (like many indexes or large datasets), it may exceed this limit. Increasing the limit allows MongoDB to handle more connections and file operations simultaneously, thus resolving the "too many open files" error.  The exact number you need will depend on your system's resources and the workload MongoDB is handling. Starting with 65536 is often a good starting point, but you might need to increase it further based on your monitoring.


## External References

* [MongoDB Documentation](https://www.mongodb.com/docs/)  (General MongoDB documentation)
* [Systemd documentation](https://www.freedesktop.org/software/systemd/man/systemd.html) (For understanding systemd unit files)
* [ulimit man page](https://man7.org/linux/man-pages/man1/ulimit.1.html) (For understanding the ulimit command)


Copyrights (c) OpenRockets Open-source Network. Free to use, copy, share, edit or publish.

