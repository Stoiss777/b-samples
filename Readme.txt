1. DB
----------------------

���������� ��� ������ � ��������� PgSQL ����� PHP

��������, ���� ������� � postgres

CREATE OR REPLACE FUNCTION "users"."get_properties_by_id"(integer)
    RETURNS TABLE ("key" varchar(255), "value" text) AS
$BODY$

    // some code here

END
$BODY$
LANGUAGE plpgsql VOLATILE 
COST 100 
ROWS 1000;


�����, ����� ����� � ��� �������� ��������� �������

$res = DB::schema('users')->getPropertiesById($userId);
while ( $row = $res->fetch() )
{
    $someKey = $row->key;
    $someVal = $row->value;
}



2. KVDB
-------------------------
������ � ������� redis ��� � ������ �������

$kvdb = new Redis('some:name:space:here');

// ��������� ��� ����� � ������ ������������ ����
foreach ( $kvdb as $key => $value )
{
    // code here
}

// �������� ����� ����
$kvdb->newKey = 'bla-bla';



3. ���������� ��� ������ � oAuth2 ������������
-------------------------
������ ��� ������������ � ����� :)