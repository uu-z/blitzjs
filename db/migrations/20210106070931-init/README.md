# Migration `20210106070931-init`

This migration has been generated by uuz at 1/6/2021, 3:09:31 PM.
You can check out the [state of the schema](./schema.prisma) after the migration.

## Database Steps

```sql
ALTER TABLE "checkin" DROP CONSTRAINT "checkin_pkey",
ALTER COLUMN "id" SET DATA TYPE TEXT,
ADD PRIMARY KEY ("id")
```

## Changes

```diff
diff --git schema.prisma schema.prisma
migration ..20210106070931-init
--- datamodel.dml
+++ datamodel.dml
@@ -1,0 +1,18 @@
+generator client {
+  provider = "prisma-client-js"
+}
+
+/// 
+datasource postgresql {
+  provider = "postgresql"
+  url = "***"
+}
+
+model checkin {
+  /// The value of this field is generated by the database as: `gen_random_uuid()`.
+  id         String   @id @default(dbgenerated())
+  user_id    String
+  ip         String
+  created_at DateTime @default(now())
+  updated_at DateTime @default(now())
+}
```


