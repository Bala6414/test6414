cat > /opt/liferaysharepv/monthly_reports/test_db.pl << 'EOF'
#!/usr/bin/perl
use lib "/home/liferay/pv_backup/lib64/perl5";
use lib "/home/liferay/pv_backup/share/perl5";
use DBI;

my $dbh = DBI->connect("dbi:ODBC:DNS", "liferayrep_dbo", "",
    { RaiseError => 0, PrintError => 1 });

if ($dbh) {
    print "Connected successfully!\n";
    $dbh->disconnect();
} else {
    print "Connection failed: " . $DBI::errstr . "\n";
}
EOF




perl /opt/liferaysharepv/monthly_reports/test_db.pl
