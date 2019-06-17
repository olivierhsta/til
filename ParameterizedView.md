# How to simulate a parameterized view in Oracle

### First step : Create a package to store the parameters

```plsql
create or replace package MYVIEW_PKG as
  procedure SET_VALUES(P_PARAM1 number, P_PARAM2 number);

  function GET_PARAM1
    return number;

  function GET_PARAM2
    return number;
end MYVIEW_PKG;

create or replace package body MYVIEW_PKG as
  V_PARAM1   number;
  V_PARAM2     number;

  procedure SET_VALUES(P_PARAM1 number, P_PARAM2 number) as
  begin
    V_FROM_DATE := P_FROMDATE;
    V_TO_DATE := P_TODATE;
  end;

  function GET_PARAM1
    return number is
  begin
    return V_PARAM1;
  end;

  function GET_PARAM2
    return date is
  begin
    return V_PARAM2;
  end;
end MYVIEW_PKG;
```

### Second step : Create the view

```
SELECT
    something1,
    something2
FROM
    table
WHERE
    param1 = MYVIEW_PKG.GET_PARAM1
  AND
    param2 = MYVIEW_PKG.GET_PARAM2
```

### Usage

##### Standard
exec MYVIEW_PKG.SET_VALUES(1,2);
select * from myview;

##### APEX
MYVIEW_PKG.SET_VALUES(1,2);
select * from myview;
