
  <li><a href="../index.html">Docs</a> &raquo;</li>
  <li><a href="">hpe3par_snapshot - Manage HPE 3PAR Snapshots</a></li>
  
    <li class="wy-breadcrumbs-aside">
      <a href="https://github.com/ansible/ansible/edit/devel/lib/ansible/modules/snap/hpe3par_snapshot.py?description=%3C!---%20Your%20description%20here%20--%3E%0A%0A%2Blabel:%20docsite_pr" class="icon icon-github"> Edit on GitHub</a>
    </li>
  
</ul>
<hr/>

          <div id="page-content">
          
  <div class="section" id="hpe3par-snapshot-manage-hpe-3par-snapshots">
<span id="hpe3par-snapshot-module"></span><h1>hpe3par_snapshot - Manage HPE 3PAR Snapshots<a class="headerlink" href="#hpe3par-snapshot-manage-hpe-3par-snapshots" title="Permalink to this headline">¶</a></h1>
<div class="versionadded">
<p><span class="versionmodified">New in version 2.4.</span></p>
</div>
<div class="contents local topic" id="contents">
<ul class="simple">
<li><a class="reference internal" href="#synopsis" id="id1">Synopsis</a><ul>
<li><a class="reference internal" href="#requirements" id="id2">Requirements</a></li>
</ul>
</li>
<li><a class="reference internal" href="#parameters" id="id3">Parameters</a></li>
<li><a class="reference internal" href="#examples" id="id4">Examples</a></li>
<li><a class="reference internal" href="#status" id="id5">Status</a></li>
<li><a class="reference internal" href="#maintenance" id="id6">Maintenance</a><ul>
<li><a class="reference internal" href="#author" id="id7">Author</a></li>
</ul>
</li>
</ul>
</div>
<div class="section" id="synopsis">
<h2><a class="toc-backref" href="#id1">Synopsis</a><a class="headerlink" href="#synopsis" title="Permalink to this headline">¶</a></h2>
<ul class="simple">
<li>On HPE 3PAR - Create Snapshot. - Delete Snapshot. - Modify Snapshot. -  Create Schedule. - Modify Schedule. - Suspend Schedule. - Resume Schedule. - Delete Schedule.</li>
</ul>
<div class="section" id="requirements">
<h3><a class="toc-backref" href="#id2">Requirements</a><a class="headerlink" href="#requirements" title="Permalink to this headline">¶</a></h3>
<p>The below requirements are needed on the host that executes this module.</p>
<ul class="simple">
<li>3PAR OS - 3.2.2 MU6, 3.3.1 MU1</li>
<li>Ansible - 2.4</li>
<li>hpe3par_sdk 1.0.0</li>
<li>WSAPI service should be enabled on the 3PAR storage array.</li>
</ul>
</div>
</div>
<div class="section" id="parameters">
<h2><a class="toc-backref" href="#id3">Parameters</a><a class="headerlink" href="#parameters" title="Permalink to this headline">¶</a></h2>
<table  border=0 cellpadding=0 class="documentation-table">
    <tr>
        <th colspan="1">Parameter</th>
        <th>Choices/<font color="blue">Defaults</font></th>
                    <th width="100%">Comments</th>
    </tr>
                <tr>
                                                            <td colspan="1">
                <b>allow_remote_copy_parent</b>
                <br/><div style="font-size: small; color: red">bool</div>                                                        </td>
                            <td>
                                                                                                                                                                    <ul><b>Choices:</b>
                                                                                                                                                            <li>no</li>
                                                                                                                                                                                            <li>yes</li>
                                                                                </ul>
                                                                        </td>
                                                            <td>
                                                                    <div>Allows the promote operation to proceed even if the RW parent volume is currently in a Remote Copy volume group, if that group has not been started. If the Remote Copy group has been started, this command fails.</div>
                                                                            </td>
        </tr>
                            <tr>
                                                            <td colspan="1">
                <b>base_volume_name</b>
                                                                        </td>
                            <td>
                                                                                                                                                        </td>
                                                            <td>
                                                                    <div>Specifies the source volume.
Required with action present</div>
                                                                            </td>
        </tr>
                            <tr>
                                                            <td colspan="1">
                <b>expiration_hours</b>
                                                                        </td>
                            <td>
                                                                                                                                                                <b>Default:</b><br/><div style="color: blue">0</div>
                                </td>
                                                            <td>
                                                                    <div>Specifies the relative time from the current time that the volume expires. Value is a positive integer and in the range of 1 to 43,800 hours, or 1825 days.</div>
                                                                            </td>
        </tr>
                            <tr>
                                                            <td colspan="1">
                <b>expiration_time</b>
                                                                        </td>
                            <td>
                                                                                                                                                        </td>
                                                            <td>
                                                                    <div>Specifies the relative time from the current time that the volume expires. Value is a positive integer and in the range of 1 to 43,800 hours, or 1825 days.</div>
                                                                            </td>
        </tr>
                            <tr>
                                                            <td colspan="1">
                <b>expiration_unit</b>
                                                                        </td>
                            <td>
                                                                                                                        <ul><b>Choices:</b>
                                                                                                                                                            <li><div style="color: blue"><b>Hours</b>&nbsp;&larr;</div></li>
                                                                                                                                                                                            <li>Days</li>
                                                                                </ul>
                                                                        </td>
                                                            <td>
                                                                    <div>Unit of Expiration Time.</div>
                                                                            </td>
        </tr>
                            <tr>
                                                            <td colspan="1">
                <b>new_name</b>
                                                                        </td>
                            <td>
                                                                                                                                                        </td>
                                                            <td>
                                                                    <div>New name of the volume.</div>
                                                                            </td>
        </tr>
                            <tr>
                                                            <td colspan="1">
                <b>new_schedule_name</b>
                                                                        </td>
                            <td>
                                                                                                                                                        </td>
                                                            <td>
                                                                    <div>New Name of the schedule.</div>
                                                                            </td>
        </tr>
                            <tr>
                                                            <td colspan="1">
                <b>priority</b>
                                                                        </td>
                            <td>
                                                                                                                        <ul><b>Choices:</b>
                                                                                                                                                            <li>HIGH</li>
                                                                                                                                                                                            <li>MEDIUM</li>
                                                                                                                                                                                            <li>LOW</li>
                                                                                </ul>
                                                                        </td>
                                                            <td>
                                                                    <div>Does not apply to online promote operation or to stop promote operation.</div>
                                                                            </td>
        </tr>
                            <tr>
                                                            <td colspan="1">
                <b>read_only</b>
                <br/><div style="font-size: small; color: red">bool</div>                                                        </td>
                            <td>
                                                                                                                                                                    <ul><b>Choices:</b>
                                                                                                                                                            <li>no</li>
                                                                                                                                                                                            <li>yes</li>
                                                                                </ul>
                                                                        </td>
                                                            <td>
                                                                    <div>Specifies that the copied volume is read-only. false(default) The volume is read/write.</div>
                                                                            </td>
        </tr>
                            <tr>
                                                            <td colspan="1">
                <b>retention_hours</b>
                                                                        </td>
                            <td>
                                                                                                                                                                <b>Default:</b><br/><div style="color: blue">0</div>
                                </td>
                                                            <td>
                                                                    <div>Specifies the relative time from the current time that the volume expires. Value is a positive integer and in the range of 1 to 43,800 hours, or 1825 days.</div>
                                                                            </td>
        </tr>
                            <tr>
                                                            <td colspan="1">
                <b>retention_time</b>
                                                                        </td>
                            <td>
                                                                                                                                                        </td>
                                                            <td>
                                                                    <div>Specifies the relative time from the current time that the volume will expire. Value is a positive integer and in the range of 1 to 43,800 hours, or 1825 days.</div>
                                                                            </td>
        </tr>
                            <tr>
                                                            <td colspan="1">
                <b>retention_unit</b>
                                                                        </td>
                            <td>
                                                                                                                        <ul><b>Choices:</b>
                                                                                                                                                            <li><div style="color: blue"><b>Hours</b>&nbsp;&larr;</div></li>
                                                                                                                                                                                            <li>Days</li>
                                                                                </ul>
                                                                        </td>
                                                            <td>
                                                                    <div>Unit of Retention Time.</div>
                                                                            </td>
        </tr>
                            <tr>
                                                            <td colspan="1">
                <b>rm_exp_time</b>
                <br/><div style="font-size: small; color: red">bool</div>                                                        </td>
                            <td>
                                                                                                                                                                    <ul><b>Choices:</b>
                                                                                                                                                            <li>no</li>
                                                                                                                                                                                            <li>yes</li>
                                                                                </ul>
                                                                        </td>
                                                            <td>
                                                                    <div>Enables (false) or disables (true) resetting the expiration time. If false, and expiration time value is a positive number, then set.</div>
                                                                            </td>
        </tr>
                            <tr>
                                                            <td colspan="1">
                <b>schedule_name</b>
                                    <br/><div style="font-size: small; color: red">required</div>                                    </td>
                            <td>
                                                                                                                                                        </td>
                                                            <td>
                                                                    <div>Name of the schedule.</div>
                                                                            </td>
        </tr>
                            <tr>
                                                            <td colspan="1">
                <b>snapshot_name</b>
                                    <br/><div style="font-size: small; color: red">required</div>                                    </td>
                            <td>
                                                                                                                                                        </td>
                                                            <td>
                                                                    <div>Specifies a snapshot volume name.</div>
                                                                            </td>
        </tr>
                            <tr>
                                                            <td colspan="1">
                <b>state</b>
                                    <br/><div style="font-size: small; color: red">required</div>                                    </td>
                            <td>
                                                                                                                        <ul><b>Choices:</b>
                                                                                                                                                            <li>present</li>
                                                                                                                                                                                            <li>absent</li>
                                                                                                                                                                                            <li>modify</li>
                                                                                                                                                                                            <li>create_schedule</li>
                                                                                                                                                                                            <li>delete_schedule</li>
                                                                                                                                                                                            <li>modify_schedule</li>
                                                                                                                                                                                            <li>suspend_schedule</li>
                                                                                                                                                                                            <li>resume_schedule</li>
                                                                                                                                                                                            <li>restore_offline</li>
                                                                                                                                                                                            <li>restore_online</li>
                                                                                </ul>
                                                                        </td>
                                                            <td>
                                                                    <div>Whether the specified Snapshot should exist or not. State also provides actions to modify and restore snapshots.</div>
                                                                            </td>
        </tr>
                            <tr>
                                                            <td colspan="1">
                <b>storage_system_ip</b>
                                    <br/><div style="font-size: small; color: red">required</div>                                    </td>
                            <td>
                                                                                                                                                        </td>
                                                            <td>
                                                                    <div>The storage system IP address.</div>
                                                                            </td>
        </tr>
                            <tr>
                                                            <td colspan="1">
                <b>storage_system_password</b>
                                    <br/><div style="font-size: small; color: red">required</div>                                    </td>
                            <td>
                                                                                                                                                        </td>
                                                            <td>
                                                                    <div>The storage system password.</div>
                                                                            </td>
        </tr>
                            <tr>
                                                            <td colspan="1">
                <b>storage_system_username</b>
                                    <br/><div style="font-size: small; color: red">required</div>                                    </td>
                            <td>
                                                                                                                                                        </td>
                                                            <td>
                                                                    <div>The storage system user name.</div>
                                                                            </td>
        </tr>
                            <tr>
                                                            <td colspan="1">
                <b>task_freq</b>
                                                                        </td>
                            <td>
                                                                                                                                                        </td>
                                                            <td>
                                                                    <div>Frequency as special string for the schedule to be created.</div>
                                                                            </td>
        </tr>
                    </table>
<br/></div>
<div class="section" id="examples">
<h2><a class="toc-backref" href="#id4">Examples</a><a class="headerlink" href="#examples" title="Permalink to this headline">¶</a></h2>
<div class="highlight-yaml+jinja notranslate"><div class="highlight"><pre><span></span><span class="p p-Indicator">-</span> <span class="nt">name</span><span class="p">:</span> <span class="l l-Scalar l-Scalar-Plain">Create Volume snasphot my_ansible_snapshot</span>
  <span class="nt">hpe3par_snapshot</span><span class="p">:</span>
    <span class="nt">storage_system_ip</span><span class="p">:</span> <span class="l l-Scalar l-Scalar-Plain">10.10.10.1</span>
    <span class="nt">storage_system_username</span><span class="p">:</span> <span class="l l-Scalar l-Scalar-Plain">username</span>
    <span class="nt">storage_system_password</span><span class="p">:</span> <span class="l l-Scalar l-Scalar-Plain">password</span>
    <span class="nt">state</span><span class="p">:</span> <span class="l l-Scalar l-Scalar-Plain">present</span>
    <span class="nt">snapshot_name</span><span class="p">:</span> <span class="l l-Scalar l-Scalar-Plain">snap-volume</span>
    <span class="nt">base_volume_name</span><span class="p">:</span> <span class="l l-Scalar l-Scalar-Plain">test_volume</span>
    <span class="nt">read_only</span><span class="p">:</span> <span class="l l-Scalar l-Scalar-Plain">False</span>
<span class="p p-Indicator">-</span> <span class="nt">name</span><span class="p">:</span> <span class="l l-Scalar l-Scalar-Plain">Restore offline Volume snasphot my_ansible_snapshot</span>
  <span class="nt">hpe3par_snapshot</span><span class="p">:</span>
    <span class="nt">storage_system_ip</span><span class="p">:</span> <span class="l l-Scalar l-Scalar-Plain">10.10.10.1</span>
    <span class="nt">storage_system_username</span><span class="p">:</span> <span class="l l-Scalar l-Scalar-Plain">username</span>
    <span class="nt">storage_system_password</span><span class="p">:</span> <span class="l l-Scalar l-Scalar-Plain">password</span>
    <span class="nt">state</span><span class="p">:</span> <span class="l l-Scalar l-Scalar-Plain">restore_offline</span>
    <span class="nt">snapshot_name</span><span class="p">:</span> <span class="l l-Scalar l-Scalar-Plain">snap-volume</span>
    <span class="nt">priority</span><span class="p">:</span> <span class="l l-Scalar l-Scalar-Plain">MEDIUM</span>
<span class="p p-Indicator">-</span> <span class="nt">name</span><span class="p">:</span> <span class="l l-Scalar l-Scalar-Plain">Restore offline Volume snasphot my_ansible_snapshot</span>
  <span class="nt">hpe3par_snapshot</span><span class="p">:</span>
    <span class="nt">storage_system_ip</span><span class="p">:</span> <span class="l l-Scalar l-Scalar-Plain">10.10.10.1</span>
    <span class="nt">storage_system_username</span><span class="p">:</span> <span class="l l-Scalar l-Scalar-Plain">username</span>
    <span class="nt">storage_system_password</span><span class="p">:</span> <span class="l l-Scalar l-Scalar-Plain">password</span>
    <span class="nt">state</span><span class="p">:</span> <span class="l l-Scalar l-Scalar-Plain">restore_online</span>
    <span class="nt">snapshot_name</span><span class="p">:</span> <span class="l l-Scalar l-Scalar-Plain">snap-volume</span>
<span class="p p-Indicator">-</span> <span class="nt">name</span><span class="p">:</span> <span class="l l-Scalar l-Scalar-Plain">Modify/rename snasphot my_ansible_snapshot</span>
        <span class="l l-Scalar l-Scalar-Plain">to my_ansible_snapshot_renamed</span>
  <span class="nt">hpe3par_snapshot</span><span class="p">:</span>
    <span class="nt">storage_system_ip</span><span class="p">:</span> <span class="l l-Scalar l-Scalar-Plain">10.10.10.1</span>
    <span class="nt">storage_system_username</span><span class="p">:</span> <span class="l l-Scalar l-Scalar-Plain">username</span>
    <span class="nt">storage_system_password</span><span class="p">:</span> <span class="l l-Scalar l-Scalar-Plain">password</span>
    <span class="nt">state</span><span class="p">:</span> <span class="l l-Scalar l-Scalar-Plain">modify</span>
    <span class="nt">snapshot_name</span><span class="p">:</span> <span class="l l-Scalar l-Scalar-Plain">snap-volume</span>
    <span class="nt">new_name</span><span class="p">:</span> <span class="l l-Scalar l-Scalar-Plain">snapshot-volume</span>
<span class="p p-Indicator">-</span> <span class="nt">name</span><span class="p">:</span> <span class="l l-Scalar l-Scalar-Plain">Delete snasphot my_ansible_snapshot_renamed</span>
  <span class="nt">hpe3par_snapshot</span><span class="p">:</span>
    <span class="nt">storage_system_ip</span><span class="p">:</span> <span class="l l-Scalar l-Scalar-Plain">10.10.10.1</span>
    <span class="nt">storage_system_username</span><span class="p">:</span> <span class="l l-Scalar l-Scalar-Plain">username</span>
    <span class="nt">storage_system_password</span><span class="p">:</span> <span class="l l-Scalar l-Scalar-Plain">password</span>
    <span class="nt">state</span><span class="p">:</span> <span class="l l-Scalar l-Scalar-Plain">absent</span>
    <span class="nt">snapshot_name</span><span class="p">:</span> <span class="l l-Scalar l-Scalar-Plain">snap-volume</span>
<span class="p p-Indicator">-</span> <span class="nt">name</span><span class="p">:</span> <span class="l l-Scalar l-Scalar-Plain">Create schedule my_ansible_sc</span>
  <span class="nt">hpe3par_snapshot</span><span class="p">:</span>
    <span class="nt">storage_system_ip</span><span class="p">:</span> <span class="l l-Scalar l-Scalar-Plain">10.10.10.1</span>
    <span class="nt">storage_system_username</span><span class="p">:</span> <span class="l l-Scalar l-Scalar-Plain">username</span>
    <span class="nt">storage_system_password</span><span class="p">:</span> <span class="l l-Scalar l-Scalar-Plain">password</span>
    <span class="nt">state</span><span class="p">:</span> <span class="l l-Scalar l-Scalar-Plain">create_schedule</span>
    <span class="nt">schedule_name</span><span class="p">:</span> <span class="l l-Scalar l-Scalar-Plain">my_ansible_sc</span>
    <span class="nt">base_volume_name</span><span class="p">:</span> <span class="l l-Scalar l-Scalar-Plain">test_volume</span>
<span class="p p-Indicator">-</span> <span class="nt">name</span><span class="p">:</span> <span class="l l-Scalar l-Scalar-Plain">Modify schedule my_ansible_sc</span>
  <span class="nt">hpe3par_snapshot</span><span class="p">:</span>
    <span class="nt">storage_system_ip</span><span class="p">:</span> <span class="l l-Scalar l-Scalar-Plain">10.10.10.1</span>
    <span class="nt">storage_system_username</span><span class="p">:</span> <span class="l l-Scalar l-Scalar-Plain">username</span>
    <span class="nt">storage_system_password</span><span class="p">:</span> <span class="l l-Scalar l-Scalar-Plain">password</span>
    <span class="nt">state</span><span class="p">:</span> <span class="l l-Scalar l-Scalar-Plain">create_schedule</span>
    <span class="nt">schedule_name</span><span class="p">:</span> <span class="l l-Scalar l-Scalar-Plain">my_ansible_sc</span>
    <span class="nt">new_schedule_name</span><span class="p">:</span> <span class="l l-Scalar l-Scalar-Plain">test_ansible_sc</span>
<span class="p p-Indicator">-</span> <span class="nt">name</span><span class="p">:</span> <span class="l l-Scalar l-Scalar-Plain">Delete schedule my_ansible_sc</span>
  <span class="nt">hpe3par_snapshot</span><span class="p">:</span>
    <span class="nt">storage_system_ip</span><span class="p">:</span> <span class="l l-Scalar l-Scalar-Plain">10.10.10.1</span>
    <span class="nt">storage_system_username</span><span class="p">:</span> <span class="l l-Scalar l-Scalar-Plain">username</span>
    <span class="nt">storage_system_password</span><span class="p">:</span> <span class="l l-Scalar l-Scalar-Plain">password</span>
    <span class="nt">state</span><span class="p">:</span> <span class="l l-Scalar l-Scalar-Plain">delete_schedule</span>
    <span class="nt">schedule_name</span><span class="p">:</span> <span class="l l-Scalar l-Scalar-Plain">my_ansible_sc</span>
</pre></div>
</div>
</div>
