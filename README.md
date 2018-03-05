FILE: README.md
VERSION: 1.0
AUTHOR:  Randy Willard
DATE:  Thu Jan 11 16:11:16 MST 2018

greenplum database healthcheck

Usage: <br/>
mkdir gp_health <br/>
tar xzf health_scripts.tgz -C gp_health <br/>
cd gp_health <br/>
./auto_health.sh <br/>
 <br/>
Script will prompt for information about your greenplum environment.  With this information it will
execute 2 scripts which analyze your operating system and your greenplum configuration.  This info
is compiled into a compressed tar file (tgz) which you should send back to your Pivotal field 
engineer.  The information included in the output will help them in assessing the overall green-
plum environment.  In some cases the field engineer may request that certain additional commands
are executed to augment the configuration and environment.  The script echoes out the file name
and location upon completion.

Components
<ul>
    <li>auto_health.sh - script that automates running the other scripts, bundles things and creates output tar ball </li>
    <li>gp_health.funcs - functions used by the .sh files.  Sourced by both scripts </li>
    <li>gp_health_os.sh - operating system assessment script </li>
    <li>gp_healthcheck.sh - greenplum assessment script </li>
    <li>run_groups - groupings of functionality for the greenpum assessment.  Simplifies running the script for
                 multiple areas.  Can be modified.  Please keep a copy of the original </li>
</ul>

Artifacts <br/>
gp_env - postgres/greenplum settings compiled from inquiries in auto_health.sh <br/>
val_all.awk - awk for processing OS command output <br/>
working_directories: - holding area for command and report output <br/>
    /tmp/gphealthcheck_01092018 <br/>
    /tmp/gpdb_os_info_01092018 <br/>

