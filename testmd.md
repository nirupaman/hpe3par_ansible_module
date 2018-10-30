source
:   snap/hpe3par\_cpg.py

orphan
:   

hpe3par\_cpg - Manage HPE 3PAR CPG
==================================

Synopsis
--------

-   Create and delete CPG on HPE 3PAR.

### Requirements

The below requirements are needed on the host that executes this module.

-   3PAR OS - 3.2.2 MU6, 3.3.1 MU1
-   Ansible - 2.4
-   hpe3par\_sdk 1.0.0
-   WSAPI service should be enabled on the 3PAR storage array.

Parameters
----------

<table  border=0 cellpadding=0 class="documentation-table">
    <tr>
        <th colspan="1">Parameter</th>
        <th>Choices/<font color="blue">Defaults</font></th>
                    <th width="100%">Comments</th>
    </tr>
                <tr>
                                                            <td colspan="1">
                <b>cpg_name</b>
                                    <br/><div style="font-size: small; color: red">required</div>                                    </td>
                            <td>
                                                                                                                                                        </td>
                                                            <td>
                                                                    <div>Name of the CPG.</div>
                                                                            </td>
        </tr>
                            <tr>
                                                            <td colspan="1">
                <b>disk_type</b>
                                                                        </td>
                            <td>
                                                                                                                        <ul><b>Choices:</b>
                                                                                                                                                            <li>FC</li>
                                                                                                                                                                                            <li>NL</li>
                                                                                                                                                                                            <li>SSD</li>
                                                                                </ul>
                                                                        </td>
                                                            <td>
                                                                    <div>Specifies that physical disks must have the specified device type.</div>
                                                                            </td>
        </tr>
                            <tr>
                                                            <td colspan="1">
                <b>domain</b>
                                                                        </td>
                            <td>
                                                                                                                                                        </td>
                                                            <td>
                                                                    <div>Specifies the name of the domain in which the object will reside.</div>
                                                                            </td>
        </tr>
                            <tr>
                                                            <td colspan="1">
                <b>growth_increment</b>
                                                                        </td>
                            <td>
                                                                                                                                                                <b>Default:</b><br/><div style="color: blue">-1.0</div>
                                </td>
                                                            <td>
                                                                    <div>Specifies the growth increment the amount of logical disk storage created on each auto-grow operation.</div>
                                                                            </td>
        </tr>
                            <tr>
                                                            <td colspan="1">
                <b>growth_increment_unit</b>
                                                                        </td>
                            <td>
                                                                                                                        <ul><b>Choices:</b>
                                                                                                                                                            <li>MiB</li>
                                                                                                                                                                                            <li><div style="color: blue"><b>GiB</b>&nbsp;&larr;</div></li>
                                                                                                                                                                                            <li>TiB</li>
                                                                                </ul>
                                                                        </td>
                                                            <td>
                                                                    <div>Unit of growth increment.</div>
                                                                            </td>
        </tr>
                            <tr>
                                                            <td colspan="1">
                <b>growth_limit</b>
                                                                        </td>
                            <td>
                                                                                                                                                                <b>Default:</b><br/><div style="color: blue">-1.0</div>
                                </td>
                                                            <td>
                                                                    <div>Specifies that the autogrow operation is limited to the specified storage amount that sets the growth limit.</div>
                                                                            </td>
        </tr>
                            <tr>
                                                            <td colspan="1">
                <b>growth_limit_unit</b>
                                                                        </td>
                            <td>
                                                                                                                        <ul><b>Choices:</b>
                                                                                                                                                            <li>MiB</li>
                                                                                                                                                                                            <li><div style="color: blue"><b>GiB</b>&nbsp;&larr;</div></li>
                                                                                                                                                                                            <li>TiB</li>
                                                                                </ul>
                                                                        </td>
                                                            <td>
                                                                    <div>Unit of growth limit.</div>
                                                                            </td>
        </tr>
                            <tr>
                                                            <td colspan="1">
                <b>growth_warning</b>
                                                                        </td>
                            <td>
                                                                                                                                                                <b>Default:</b><br/><div style="color: blue">-1.0</div>
                                </td>
                                                            <td>
                                                                    <div>Specifies that the threshold of used logical disk space when exceeded results in a warning alert.</div>
                                                                            </td>
        </tr>
                            <tr>
                                                            <td colspan="1">
                <b>growth_warning_unit</b>
                                                                        </td>
                            <td>
                                                                                                                        <ul><b>Choices:</b>
                                                                                                                                                            <li>MiB</li>
                                                                                                                                                                                            <li><div style="color: blue"><b>GiB</b>&nbsp;&larr;</div></li>
                                                                                                                                                                                            <li>TiB</li>
                                                                                </ul>
                                                                        </td>
                                                            <td>
                                                                    <div>Unit of growth warning.</div>
                                                                            </td>
        </tr>
                            <tr>
                                                            <td colspan="1">
                <b>high_availability</b>
                                                                        </td>
                            <td>
                                                                                                                        <ul><b>Choices:</b>
                                                                                                                                                            <li>PORT</li>
                                                                                                                                                                                            <li>CAGE</li>
                                                                                                                                                                                            <li>MAG</li>
                                                                                </ul>
                                                                        </td>
                                                            <td>
                                                                    <div>Specifies that the layout must support the failure of one port pair, one cage, or one magazine.</div>
                                                                            </td>
        </tr>
                            <tr>
                                                            <td colspan="1">
                <b>raid_type</b>
                                                                        </td>
                            <td>
                                                                                                                        <ul><b>Choices:</b>
                                                                                                                                                            <li>R0</li>
                                                                                                                                                                                            <li>R1</li>
                                                                                                                                                                                            <li>R5</li>
                                                                                                                                                                                            <li>R6</li>
                                                                                </ul>
                                                                        </td>
                                                            <td>
                                                                    <div>Specifies the RAID type for the logical disk.</div>
                                                                            </td>
        </tr>
                            <tr>
                                                            <td colspan="1">
                <b>set_size</b>
                                                                        </td>
                            <td>
                                                                                                                                                                <b>Default:</b><br/><div style="color: blue">-1</div>
                                </td>
                                                            <td>
                                                                    <div>Specifies the set size in the number of chunklets.</div>
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
                                                                                </ul>
                                                                        </td>
                                                            <td>
                                                                    <div>Whether the specified CPG should exist or not.</div>
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
                    </table>
<br/>
Examples
--------

``` {.sourceCode .yaml+jinja}
- name: Create CPG "{{ cpg_name }}"
  hpe3par_cpg:
    storage_system_ip="{{ storage_system_ip }}"
    storage_system_username="{{ storage_system_username }}"
    storage_system_password="{{ storage_system_password }}"
    state=present
    cpg_name="{{ cpg_name }}"
    domain="{{ domain }}"
    growth_increment="{{ growth_increment }}"
    growth_increment_unit="{{ growth_increment_unit }}"
    growth_limit="{{ growth_limit }}"
    growth_limit_unit="{{ growth_limit_unit }}"
    growth_warning="{{ growth_warning }}"
    growth_warning_unit="{{ growth_warning_unit }}"
    raid_type="{{ raid_type }}"
    set_size="{{ set_size }}"
    high_availability="{{ high_availability }}"
    disk_type="{{ disk_type }}"

- name: Delete CPG "{{ cpg_name }}"
  hpe3par_cpg:
    storage_system_ip="{{ storage_system_ip }}"
    storage_system_username="{{ storage_system_username }}"
    storage_system_password="{{ storage_system_password }}"
    state=absent
    cpg_name="{{ cpg_name }}"
```

Status
------

This module is flagged as **preview** which means that it is not
guaranteed to have a backwards compatible interface.

Maintenance
-----------

This module is flagged as **community** which means that it is
maintained by the Ansible Community. See
Module Maintenance & Support \<modules\_support\> for more info.

For a list of other modules that are also maintained by the Ansible
Community, see here \<community\_supported\>.

### Author

-   Hewlett Packard Enterprise (<ecostor@groups.ext.hpe.com>)

> **hint**
>
> If you notice any issues in this documentation you can [edit this
> document](https://github.com/ansible/ansible/edit/devel/lib/ansible/modules/snap/hpe3par_cpg.py?description=%3C!---%20Your%20description%20here%20--%3E%0A%0A%2Blabel:%20docsite_pr)
> to improve it.

