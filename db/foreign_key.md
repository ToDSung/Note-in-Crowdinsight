# 外鍵約束

建立外鍵時 透過設定 on_delete

CASCAD 刪除該外鍵索引時，會相應的刪除全部 row data
SET NULL 會設定為 NULL
NO ACTION 不好的做法
RESTRICT 拒絕刪除