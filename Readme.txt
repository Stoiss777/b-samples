1. DB
----------------------

Библиотека для работы с функциями PgSQL через PHP

Например, есть функция в postgres

CREATE OR REPLACE FUNCTION "users"."get_properties_by_id"(integer)
    RETURNS TABLE ("key" varchar(255), "value" text) AS
$BODY$

    // some code here

END
$BODY$
LANGUAGE plpgsql VOLATILE 
COST 100 
ROWS 1000;


Тогда, можно будет с ней работать следующим образом

$res = DB::schema('users')->getPropertiesById($userId);
while ( $row = $res->fetch() )
{
    $someKey = $row->key;
    $someVal = $row->value;
}



2. KVDB
-------------------------
Работа с ключами redis как с полями объекта

$kvdb = new Redis('some:name:space:here');

// перебрать все ключи в данном пространстве имен
foreach ( $kvdb as $key => $value )
{
    // code here
}

// добавить новый ключ
$kvdb->newKey = 'bla-bla';



3. Библиотека для работы с oAuth2 авторизацией
-------------------------
Просто для ознакомления с кодом :)