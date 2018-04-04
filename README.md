# text


TMP=/tmp; export TMP
TMPDIR=$TMP; export TMPDIR

ORACLE_HOSTNAME=oracle-server.midominio; export ORACLE_HOSTNAME
ORACLE_BASE=/oracle/app/oracle; export ORACLE_BASE
ORACLE_HOME=$ORACLE_BASE/product/11.2.0/db_1; export ORACLE_HOME
ORACLE_SID=ora11g; export ORACLE_SID
ORACLE_TERM=xterm; export ORACLE_TERM
PATH=$ORACLE_HOME/bin:/usr/sbin:$PATH; export PATH

LD_LIBRARY_PATH=$ORACLE_HOME/lib:/lib:/usr/lib;
export LD_LIBRARY_PATH
CLASSPATH=$ORACLE_HOME/JRE:$ORACLE_HOME/jlib:$ORACLE_HOME/rdbms/jlib;
export CLASSPATH

if [ $USER = "oracle" ]; then
   if [ $SHELL = "/bin/ksh" ]; then
     ulimit -p 16384
     ulimit -n 65536
   else
     ulimit -u 16384 -n 65536
   fi
fi

umask 022
