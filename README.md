FILE: README.md
VERSION: 1.0
AUTHOR:  Randy Willard
DATE:  Thu Jan 11 16:11:16 MST 2018

greenplum database healthcheck

Usage:
mkdir gp_health
tar xzf health_scripts.tgz -C gp_health
cd gp_health
./auto_health.sh

Script will prompt for information about your greenplum environment.  With this information it will
execute 2 scripts which analyze your operating system and your greenplum configuration.  This info
is compiled into a compressed tar file (tgz) which you should send back to your Pivotal field 
engineer.  The information included in the output will help them in assessing the overall green-
plum environment.  In some cases the field engineer may request that certain additional commands
are executed to augment the configuration and environment.  The script echoes out the file name
and location upon completion.

Components
    auto_health.sh - script that automates running the other scripts, bundles things and creates output tar ball
    gp_health.funcs - functions used by the .sh files.  Sourced by both scripts
    gp_health_os.sh - operating system assessment script
    gp_healthcheck.sh - greenplum assessment script
    run_groups - groupings of functionality for the greenpum assessment.  Simplifies running the script for
                 multiple areas.  Can be modified.  Please keep a copy of the original

Artifacts
gp_env - postgres/greenplum settings compiled from inquiries in auto_health.sh
val_all.awk - awk for processing OS command output
working_directories: - holding area for command and report output
    /tmp/gphealthcheck_01092018
    /tmp/gpdb_os_info_01092018

