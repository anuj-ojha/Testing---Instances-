UPGRADE PAYLOADS
# HotWax Maarg v5.5.18 → v6.1.11

## Scope and source rule
Included payloads are taken exactly from the release tags advanced by `hotwax-maarg-docker-config v6.1.11`. A component is shown only when its release contains UpgradeData.xml and/or a relevant upgrade SQL file. No values have been reworded or substituted.

### hotwax-maarg-util
**Release tag:** v4.0.0-RC1    **Exact file:** upgrade/v4.0.0-RC1/UpgradeData.xml    **Type:** XML

```xml
<?xml version="1.0" encoding="UTF-8"?>
<entity-facade-xml type="ext-upgrade">
    <moqui.basic.Enumeration enumId="MaargSecGrp" description="Maarg Security group mapping"/>

    <!--PWA APPs for versioned app management-->
    <co.hotwax.app.CommerceApp appId="BOPIS" appName="Bopis"/>
    <co.hotwax.app.CommerceApp appId="FULFILLMENT" appName="Fulfillment"/>
    <co.hotwax.app.CommerceApp appId="RECEIVING" appName="Receiving"/>
    <co.hotwax.app.CommerceApp appId="CYCLE_COUNT" appName="Cycle Count"/>
    <co.hotwax.app.CommerceApp appId="JOB_MANAGER" appName="Job Manager"/>
    <co.hotwax.app.CommerceApp appId="USERS" appName="Users"/>
    <co.hotwax.app.CommerceApp appId="FACILITIES" appName="Facilities"/>
    <co.hotwax.app.CommerceApp appId="PREORDER" appName="Preorder"/>
    <co.hotwax.app.CommerceApp appId="ATP" appName="Available to promise"/>
    <co.hotwax.app.CommerceApp appId="ORDER_ROUTING" appName="Order Routing"/>
    <co.hotwax.app.CommerceApp appId="TRANSFERS" appName="Transfers"/>
    <co.hotwax.app.CommerceApp appId="COMPANY" appName="Company"/>
    <co.hotwax.app.CommerceApp appId="PRODUCTS" appName="Products"/>
    <co.hotwax.app.CommerceApp appId="ORDER_MANAGER" appName="Order Manager"/>
    <co.hotwax.app.CommerceApp appId="LAUNCHPAD" appName="Launchpad"/>
    <moqui.basic.Enumeration enumId="MaargSecGrp" description="Maarg Security group mapping"/>

    <!-- Deny the default Moqui REST endpoints (/rest/s1/moqui service API, /rest/m1 entity master API) for all users;
         AUTHZT_DENY is overridable: grant a group AUTHZT_ALWAYS on this artifact group to allow it (done for ADMIN below) -->
    <moqui.security.ArtifactGroup artifactGroupId="DEFAULT_REST_API" description="Default Moqui REST Endpoints (/rest/s1/moqui, /rest/m1)"/>
    <moqui.security.ArtifactGroupMember artifactGroupId="DEFAULT_REST_API" artifactTypeEnumId="AT_REST_PATH"
                                        inheritAuthz="Y" artifactName="/moqui"/>
    <moqui.security.ArtifactGroupMember artifactGroupId="DEFAULT_REST_API" artifactTypeEnumId="AT_XML_SCREEN_TRANS"
                                        inheritAuthz="Y" artifactName="component://webroot/screen/webroot/rest.xml/m1"/>
    <moqui.security.ArtifactAuthz artifactAuthzId="DEFAULT_REST_DENY_ALL" userGroupId="ALL_USERS" artifactGroupId="DEFAULT_REST_API"
                                  authzTypeEnumId="AUTHZT_DENY" authzActionEnumId="AUTHZA_ALL"/>
    <moqui.security.ArtifactAuthz artifactAuthzId="DEFAULT_REST_ADMIN" userGroupId="ADMIN" artifactGroupId="DEFAULT_REST_API"
                                  authzTypeEnumId="AUTHZT_ALWAYS" authzActionEnumId="AUTHZA_ALL"/>

    <moqui.basic.email.EmailTemplate emailTemplateId="APP_USER_PWD_RET" description="Application User Password Reset"
        emailServerId="SYSTEM" emailTypeEnumId="EMT_PWD_RESET" webappName="webroot" sendPartial="Y"
        bodyScreenLocation="component://maarg-util/screen/email/AppUserPasswordReset.xml" fromAddress=""
        fromName="HotWax Commerce" subject="Reset Your Password"/>
</entity-facade-xml>
```

### hotwax-maarg-util
**Release tag:** v4.0.1    **Exact file:** upgrade/v4.0.1/UpgradeData.xml    **Type:** XML

```xml
<?xml version="1.0" encoding="UTF-8"?>
<entity-facade-xml type="ext-upgrade">
</entity-facade-xml>
```

### hotwax-maarg-util
**Release tag:** v4.0.3    **Exact file:** upgrade/v4.0.3/UpgradeData.xml    **Type:** XML

```xml
<?xml version="1.0" encoding="UTF-8"?>
<entity-facade-xml type="ext-upgrade">
    <moqui.basic.StatusFlowTransition statusFlowId="Default" statusId="SmsgSending" toStatusId="SmsgError" transitionName="Error"/>
</entity-facade-xml>
```

### hotwax-maarg-util
**Release tag:** v4.0.4    **Exact file:** upgrade/v4.0.4/UpgradeData.xml    **Type:** XML

```xml
<?xml version="1.0" encoding="UTF-8"?>
<entity-facade-xml type="ext-upgrade">
</entity-facade-xml>
```

### hotwax-maarg-util
**Release tag:** v4.0.4    **Exact file:** upgrade/v4.0.4/UpgradeSql.sql    **Type:** SQL

```sql
CREATE INDEX IDX_DML_CNTLOC
    ON DATA_MANAGER_LOG (CONTENT_LOCATION);
```

### hotwax-maarg-util
**Release tag:** v4.1.0    **Exact file:** upgrade/v4.1.0/UpgradeData.xml    **Type:** XML

```xml
<?xml version="1.0" encoding="UTF-8"?>
<entity-facade-xml type="ext-upgrade">
    <moqui.basic.StatusFlowTransition statusFlowId="Default" statusId="SmsgSending" toStatusId="SmsgError" transitionName="Error"/>

    <moqui.basic.Enumeration description="User Access" enumId="UgtUserAccess" enumTypeId="UserGroupType"/>
    <moqui.security.UserGroup userGroupId="ADMIN" groupTypeEnumId="UgtUserAccess"/>
    <moqui.security.UserGroup userGroupId="CSR" description="Customer Service Representatives" groupTypeEnumId="UgtUserAccess"/>
    <moqui.security.UserGroup userGroupId="STORE_MANAGER" description="Store Managers" groupTypeEnumId="UgtUserAccess"/>
    <moqui.security.UserGroup userGroupId="ORDER_MANAGER" description="Order Managers" groupTypeEnumId="UgtUserAccess"/>
    <moqui.security.UserGroup userGroupId="WAREHOUSE_MANAGER" description="Warehouse Managers" groupTypeEnumId="UgtUserAccess"/>
    <moqui.security.UserGroup userGroupId="MERCHANDISE_MGR" description="Merchandise Managers" groupTypeEnumId="UgtUserAccess"/>
</entity-facade-xml>
```

### hotwax-maarg-util
**Release tag:** v4.1.1    **Exact file:** upgrade/v4.1.1/UpgradeData.xml    **Type:** XML

```xml
<?xml version="1.0" encoding="UTF-8"?>
<entity-facade-xml type="ext-upgrade">
</entity-facade-xml>
```

### hotwax-maarg-util
**Release tag:** v4.1.2    **Exact file:** upgrade/v4.1.2/UpgradeData.xml    **Type:** XML

```xml
<?xml version="1.0" encoding="UTF-8"?>
<entity-facade-xml type="ext-upgrade">
</entity-facade-xml>
```

### hotwax-maarg-util
**Release tag:** v4.1.3    **Exact file:** upgrade/v4.1.3/UpgradeData.xml    **Type:** XML

```xml
<?xml version="1.0" encoding="UTF-8"?>
<entity-facade-xml type="ext-upgrade">
</entity-facade-xml>
```

### hotwax-maarg-util
**Release tag:** v4.1.4    **Exact file:** upgrade/v4.1.4/UpgradeData.xml    **Type:** XML

```xml
<?xml version="1.0" encoding="UTF-8"?>
<entity-facade-xml type="ext-upgrade">
</entity-facade-xml>
```

### hotwax-maarg-util
**Release tag:** v4.1.5    **Exact file:** upgrade/v4.1.5/UpgradeData.xml    **Type:** XML

```xml
<?xml version="1.0" encoding="UTF-8"?>
<entity-facade-xml type="ext-upgrade">
</entity-facade-xml>
```

### ofbiz-oms-udm
**Release tag:** v4.0.0-RC1    **Exact file:** upgrade/v4.0.0-RC1/UpgradeData.xml    **Type:** XML

```xml
<?xml version="1.0" encoding="UTF-8"?>

<!-- Customer 360 reference data for upgrading existing instances.
     Mirrors the rows added to DC_ExtSeed_BPartySeedData.xml (loaded on fresh installs). -->
<entity-facade-xml type="ext-upgrade">
    <!-- Duplicate marker + personal (blood) relationship taxonomy -->
    <org.apache.ofbiz.party.party.PartyRelationshipType partyRelationshipTypeId="DUPLICATE" hasTable="N" partyRelationshipName="Duplicate"/>
    <org.apache.ofbiz.party.party.PartyRelationshipType partyRelationshipTypeId="PERSONAL_REL" hasTable="N" partyRelationshipName="Personal Relationship"/>
    <org.apache.ofbiz.party.party.PartyRelationshipType partyRelationshipTypeId="BLOOD_REL" parentTypeId="PERSONAL_REL" hasTable="N" partyRelationshipName="Blood Relative"/>
    <org.apache.ofbiz.party.party.PartyRelationshipType partyRelationshipTypeId="MOTHER" parentTypeId="BLOOD_REL" hasTable="N" partyRelationshipName="Mother"/>
    <org.apache.ofbiz.party.party.PartyRelationshipType partyRelationshipTypeId="FATHER" parentTypeId="BLOOD_REL" hasTable="N" partyRelationshipName="Father"/>
    <org.apache.ofbiz.party.party.PartyRelationshipType partyRelationshipTypeId="CHILD" parentTypeId="BLOOD_REL" hasTable="N" partyRelationshipName="Child"/>
    <org.apache.ofbiz.party.party.PartyRelationshipType partyRelationshipTypeId="SIBLING" parentTypeId="BLOOD_REL" hasTable="N" partyRelationshipName="Sibling"/>
    <!-- External customer identifier (Kustomer) -->
    <org.apache.ofbiz.party.party.PartyIdentificationType partyIdentificationTypeId="KUSTOMER_CUST_ID" hasTable="N" description="Kustomer Customer Id"/>

    <Enumeration description="Dev" enumCode="AppEnvDev" enumId="AppEnvDev" enumTypeId="AppEnvironment" sequenceId="01"/>
    <moqui.basic.StatusFlowTransition statusFlowId="Default" statusId="RETURN_REQUESTED" toStatusId="RETURN_COMPLETED" transitionName="Requested Return Completed"/>

    <!-- Shopify Payments gateway payment method type.
         Mirrors the row added to data/DT_ExtSeed_ShopifySeedData.xml (loaded on fresh installs). -->
    <org.apache.ofbiz.accounting.payment.PaymentMethodType paymentMethodTypeId="EXT_SHOP_PAYMENTS" description="Ext Shopify Payments" paymentMethodCode="shopify_payments"/>
</entity-facade-xml>
```

### ofbiz-oms-udm
**Release tag:** v4.0.0-RC1    **Exact file:** upgrade/v4.0.0-RC1/UpgradeSql.sql    **Type:** SQL

```sql
-- ProductFacility
UPDATE PRODUCT_FACILITY 
SET LAST_UPDATED_TX_STAMP = LAST_UPDATED_STAMP 
WHERE LAST_UPDATED_TX_STAMP IS NULL;

-- ContactMech
UPDATE CONTACT_MECH 
SET LAST_UPDATED_TX_STAMP = LAST_UPDATED_STAMP 
WHERE LAST_UPDATED_TX_STAMP IS NULL;

-- PostalAddress
UPDATE POSTAL_ADDRESS 
SET LAST_UPDATED_TX_STAMP = LAST_UPDATED_STAMP 
WHERE LAST_UPDATED_TX_STAMP IS NULL;

-- OrderHeader
UPDATE ORDER_HEADER 
SET LAST_UPDATED_TX_STAMP = LAST_UPDATED_STAMP 
WHERE LAST_UPDATED_TX_STAMP IS NULL;

-- OrderItem
UPDATE ORDER_ITEM 
SET LAST_UPDATED_TX_STAMP = LAST_UPDATED_STAMP 
WHERE LAST_UPDATED_TX_STAMP IS NULL;

-- OrderItemShipGroup
UPDATE ORDER_ITEM_SHIP_GROUP 
SET LAST_UPDATED_TX_STAMP = LAST_UPDATED_STAMP 
WHERE LAST_UPDATED_TX_STAMP IS NULL;

-- OrderContactMech
UPDATE ORDER_CONTACT_MECH 
SET LAST_UPDATED_TX_STAMP = LAST_UPDATED_STAMP 
WHERE LAST_UPDATED_TX_STAMP IS NULL;

-- Drop Foreign Key constraints referencing USER_LOGIN for business entities

-- Order entities
ALTER TABLE ORDER_ADJUSTMENT DROP FOREIGN KEY ORDER_ADJ_USERL;
ALTER TABLE ORDER_HEADER DROP FOREIGN KEY ORDER_HDR_CBUL;
ALTER TABLE ORDER_ITEM DROP FOREIGN KEY ORDER_ITEM_DCUL;
ALTER TABLE ORDER_ITEM DROP FOREIGN KEY ORDER_ITEM_USRLGN;
ALTER TABLE ORDER_ITEM_CHANGE DROP FOREIGN KEY ORDER_ITCH_USER;
ALTER TABLE ORDER_PAYMENT_PREFERENCE DROP FOREIGN KEY ORDER_PMPRF_USRL;
ALTER TABLE ORDER_STATUS DROP FOREIGN KEY ORDER_STTS_USER;
ALTER TABLE RETURN_ADJUSTMENT DROP FOREIGN KEY RETURN_ADJ_USERL;
ALTER TABLE RETURN_STATUS DROP FOREIGN KEY RTN_STTS_USRLGN;

-- Shipment entities
ALTER TABLE ITEM_ISSUANCE DROP FOREIGN KEY ITEM_ISS_IBUL;
ALTER TABLE PICKLIST_ROLE DROP FOREIGN KEY PCKLST_RLE_CBUL;
ALTER TABLE PICKLIST_ROLE DROP FOREIGN KEY PCKLST_RLE_LMUL;
ALTER TABLE PICKLIST_STATUS_HISTORY DROP FOREIGN KEY PCKLST_STHST_CUL;
ALTER TABLE SHIPMENT_RECEIPT DROP FOREIGN KEY SHP_RCPT_USERLGN;
ALTER TABLE SHIPMENT_STATUS DROP FOREIGN KEY SHPMNT_STTS_USRLGN;

-- Inventory & Product entities
ALTER TABLE INVENTORY_ITEM_STATUS DROP FOREIGN KEY INV_ITEM_STTS_USER;
ALTER TABLE PRODUCT_PRICE DROP FOREIGN KEY PROD_PRICE_CBUL;
ALTER TABLE PRODUCT_PRICE DROP FOREIGN KEY PROD_PRICE_LMBUL;
ALTER TABLE PRODUCT DROP FOREIGN KEY PROD_CB_USERLOGIN;
ALTER TABLE PRODUCT DROP FOREIGN KEY PROD_LMB_USERLOGIN;

-- Party & Content entities
ALTER TABLE PARTY DROP FOREIGN KEY PARTY_CUL;
ALTER TABLE PARTY DROP FOREIGN KEY PARTY_LMCUL;
ALTER TABLE PARTY_STATUS DROP FOREIGN KEY PARTY_STTS_USRLGN;
ALTER TABLE CONTENT DROP FOREIGN KEY CONTENT_CB_ULGN;
ALTER TABLE CONTENT DROP FOREIGN KEY CONTENT_LMB_ULGN;
ALTER TABLE CONTENT_ASSOC DROP FOREIGN KEY CONTENTASSC_CBUSR;
ALTER TABLE CONTENT_ASSOC DROP FOREIGN KEY CONTENTASSC_LMBUR;
ALTER TABLE DATA_RESOURCE DROP FOREIGN KEY DATA_REC_CB_ULGN;
ALTER TABLE DATA_RESOURCE DROP FOREIGN KEY DATA_REC_LMB_ULGN;

-- App & Utility entities
ALTER TABLE USER_LOGIN_FIREBASE_CLIENT DROP FOREIGN KEY FC_USER_LOGIN;
ALTER TABLE ORDER_FACILITY_CHANGE DROP FOREIGN KEY ORDER_FAC_CH_USER;
ALTER TABLE ORDER_FACILITY_CHANGE DROP FOREIGN KEY ROUTING_USER;
ALTER TABLE ORDER_INV_PROMISE_HISTORY DROP FOREIGN KEY USER_LOGIN_REL;
ALTER TABLE USER_SEARCH_PREFERENCE DROP FOREIGN KEY USERLOGIN;
ALTER TABLE INVOICE_STATUS DROP FOREIGN KEY INV_STTS_USRLGN;

-- Drop foreign key constraints pointing to party_role
ALTER TABLE PRODUCT_STORE_ROLE DROP FOREIGN KEY PRDSTRRLE_PRLE;
ALTER TABLE CONTENT_ROLE DROP FOREIGN KEY CNTNT_RL_PTRL;
ALTER TABLE COMMUNICATION_EVENT_ROLE DROP FOREIGN KEY COM_EVRL_PRLE;
ALTER TABLE PARTY_CONTACT_MECH DROP FOREIGN KEY PARTY_CMECH_PROLE;
ALTER TABLE PARTY_RELATIONSHIP DROP FOREIGN KEY PARTY_REL_FPROLE;
ALTER TABLE ORDER_ROLE DROP FOREIGN KEY ORDER_ROLE_PROLE;
```

### mantle-shopify-connector
**Release tag:** v4.0.0-RC1    **Exact file:** upgrade/v4.0.0-RC1/UpgradeData.xml    **Type:** XML

```xml
<?xml version="1.0" encoding="UTF-8"?>
<entity-facade-xml type="ext-upgrade">
    <artifactGroups artifactGroupId="SOB_APP" description="Shopify oms bridge app">
        <artifacts artifactName="component://shopify-connector/screen/ShopifyOmsBridge.xml" artifactTypeEnumId="AT_XML_SCREEN" inheritAuthz="Y"/>
        <artifacts artifactName="/sob" artifactTypeEnumId="AT_REST_PATH" inheritAuthz="Y" />
        <!-- Full permissions for the ADMIN user group -->
        <authz artifactAuthzId="SOB_APP_ADMIN" userGroupId="ADMIN" authzTypeEnumId="AUTHZT_ALWAYS" authzActionEnumId="AUTHZA_ALL"/>
    </artifactGroups>

    <!-- Granular Shopify OAuth access scopes for scope-aware GraphQL query rendering
         (see co.hotwax.shopify.ShopifyShopAppAccessScope and OrderUnifiedMegaQuery.ftl).
         enumId intentionally equals the literal Shopify scope handle. -->
    <moqui.basic.EnumerationType description="Shopify API Access Scope" enumTypeId="ShopifyApiAccessScope"/>
    <moqui.basic.Enumeration enumId="read_orders" enumCode="read_orders" description="Read orders, transactions and fulfillments" enumTypeId="ShopifyApiAccessScope"/>
    <moqui.basic.Enumeration enumId="read_customers" enumCode="read_customers" description="Read customers" enumTypeId="ShopifyApiAccessScope"/>
    <moqui.basic.Enumeration enumId="read_returns" enumCode="read_returns" description="Read returns and reverse fulfillment orders" enumTypeId="ShopifyApiAccessScope"/>
    <moqui.basic.Enumeration enumId="read_payment_terms" enumCode="read_payment_terms" description="Read payment terms and outstanding order balances" enumTypeId="ShopifyApiAccessScope"/>

    <!-- Shopify Fulfillment Location Sync (issue hotwax/mantle-shopify-connector#399). Mirrors
         data/AA_ExtSeed_ShopifySyncHoldTypeData.xml so instances that only run upgrade data (not a full
         ext-seed reload) also get these reference-data rows. -->
    <moqui.basic.Enumeration enumId="SHPFY_SYNC_ERR" enumTypeId="RESOLVE_ONHOLD_ORDER"
            description="Shopify Fulfillment Location Sync Exception" sequenceNum="4"/>
    <!-- shopifyLocationSync opt-in switch, stored as a ProductStoreSetting keyed by this enumId - see
         AA_ExtSeed_ShopifySyncHoldTypeData.xml for the full description. -->
    <moqui.basic.Enumeration enumId="SHPFY_LOC_SYNC" enumTypeId="PROD_STR_STNG"
            description="Shopify Fulfillment Location Sync - inbound webhook opt-in switch (issue #399)"
            enumName="Shopify Fulfillment Location Sync"/>

    <moqui.basic.EnumerationType enumTypeId="SsrptPurpose" description="Shopify Shop Remote Purpose"/>
    <moqui.basic.Enumeration enumId="SsctShopifyDefaultApp" enumTypeId="SsrptPurpose" description="Default App" sequenceNum="1"/>
</entity-facade-xml>
```

### mantle-shopify-connector
**Release tag:** v4.0.0-RC1    **Exact file:** upgrade/v4.0.0-RC1/UpgradeSQL.sql    **Type:** SQL

```sql
-- ******************************************************************
-- Widen ShopifyShopAppAccessScope.accessScopeEnumId from 'id' (VARCHAR(40)) to 'text-short'
-- (VARCHAR(63)) - write_merchant_managed_fulfillment_orders is 41 characters, one over the old
-- limit, and was failing to store on already-created tables (MysqlDataTruncation). Only needed on
-- instances that already have this table; a fresh install picks up VARCHAR(63) from the entity
-- definition directly. NOT NULL is required in the same statement - MySQL rejects a bare MODIFY
-- COLUMN on a primary-key column that omits it.
-- ******************************************************************
ALTER TABLE SHOPIFY_SHOP_APP_ACCESS_SCOPE MODIFY COLUMN ACCESS_SCOPE_ENUM_ID VARCHAR(63) NOT NULL;
```

### mantle-shopify-connector
**Release tag:** v4.1.0    **Exact file:** upgrade/v4.1.0/UpgradeData.xml    **Type:** XML

```xml
<?xml version="1.0" encoding="UTF-8"?>
<entity-facade-xml type="ext-upgrade">
    <!-- shopifyLocationSync moved off ProductStoreSetting (v4.0.0-RC1) onto this component's own
         ShopifyShopSetting entity, scoped by shopId instead of productStoreId - see
         data/AA_ExtSeed_ShopifySyncHoldTypeData.xml for the full description. Re-seeding the same
         enumId with the new enumTypeId updates the existing row in place (Enumeration's PK is enumId
         alone), so no separate migration service is needed for the reference data itself - just the
         instance data (see UpgradeSteps.md). -->
    <moqui.basic.EnumerationType enumTypeId="SHOPIFY_SHOP_STNG" description="Shopify Shop Setting"/>
    <moqui.basic.Enumeration enumId="SHPFY_LOC_SYNC" enumTypeId="SHOPIFY_SHOP_STNG"
        description="Shopify Fulfillment Location Sync - inbound webhook opt-in switch (issue #399)"
        enumName="Shopify Fulfillment Location Sync"/>

    <!-- Add the systemMessageRemoteId for ShopifyShop resolution to avoid multiple SMR conflicts happening due to domain resolution -->
    <moqui.service.job.ServiceJob jobName="consume_ShopifyOrders_SQS">
        <parameters parameterName="shopifyShopSystemMessageRemoteId" parameterValue=""/>
    </moqui.service.job.ServiceJob>
    <co.hotwax.datamanager.DataManagerConfig configId="SYNC_SHP_PRD_LOC_ACT"
         importServiceName="co.hotwax.sob.product.InventoryServices.import#ShopifyProductLocationActivation"
         description="Records product-location activations confirmed by Shopify"
         executionModeId="DMC_QUEUE"/>

    <moqui.service.message.SystemMessageType systemMessageTypeId="BulkActivateShopifyProductLocations"
        description="Activate Shopify products at mapped locations"
        parentTypeId="ShopifyBulkImport"
        sendServiceName="co.hotwax.shopify.system.ShopifySystemMessageServices.send#BulkMutationSystemMessage"
        sendPath="component://shopify-connector/template/graphQL/BulkActivateShopifyProductLocations.ftl"
        consumeServiceName="co.hotwax.sob.product.InventoryServices.consume#ShopifyProductLocationActivationResult"
        receivePath="${contentRoot}/shopify/ProductLocationActivation/result/BulkOperationResult-${systemMessageId}-${remoteMessageId}-${nowDate}.jsonl"/>

    <moqui.basic.Enumeration enumId="ACT_SHPFY_PRD_LOC" enumCode="ACT_SHPFY_PRD_LOC"
        description="Activate Products on Shopify" enumTypeId="PRODUCT_SYS_JOB"/>
    <Product productId="ACT_SHPFY_PRD_LOC" productTypeId="SERVICE" internalName="ACT_SHPFY_PRD_LOC"
        productName="Activate Products on Shopify"
        description="Activate Shopify products at mapped locations and record Shopify confirmation"
        primaryProductCategoryId="PRODUCT_SYS_JOB"/>
    <ProductCategoryMember productId="ACT_SHPFY_PRD_LOC" productCategoryId="PRODUCT_SYS_JOB" fromDate="2024-01-01 00:00:00.0"/>
    <moqui.service.job.ServiceJob jobName="migrate_ShopifyProductLocationActivationTimestamp"
        description="Backfill activatedAt on existing Shopify product-location activation rows"
        serviceName="co.hotwax.sob.product.ProductMigrationServices.migrate#ShopifyProductLocationActivationTimestamp"
        cronExpression="0 * * * * ?" repeatCount="1" paused="N" priority="1">
        <parameters parameterName="batchSize" parameterValue="1000"/>
    </moqui.service.job.ServiceJob>
    <moqui.service.job.ServiceJob jobName="sync_ShopifyProductFacilityActivation"
        jobTypeEnumId="ACT_SHPFY_PRD_LOC" instanceOfProductId="ACT_SHPFY_PRD_LOC"
        description="Queue pending product-facility activations for Shopify"
        serviceName="co.hotwax.sob.product.InventoryServices.sync#ShopifyProductFacilityActivation"
        cronExpression="0 0/15 * * * ?" paused="Y">
        <parameters parameterName="shopId" parameterValue=""/>
        <parameters parameterName="facilityId" parameterValue=""/>
        <parameters parameterName="productId" parameterValue=""/>
        <parameters parameterName="maxRecords" parameterValue="250000"/>
    </moqui.service.job.ServiceJob>

    <!-- Return Lifecycle App Mapping Enumeration and Upgrade Mapping -->
    <moqui.basic.Enumeration enumId="RETURN_LIFE_CYCLE" enumTypeId="SHOPIFY_TYPE" description="Return Lifecycle App Mapping"/>
  
    <!-- Add the systemMessageRemoteId for ShopifyShop resolution to avoid multiple SMR conflicts happening due to domain resolution -->
    <moqui.service.job.ServiceJob jobName="consume_ShopifyOrders_SQS">
        <parameters parameterName="shopifyShopSystemMessageRemoteId" parameterValue=""/>
    </moqui.service.job.ServiceJob>

    <!-- SHOPIFY_POS_API authorizations for the application user groups, moved here from
         component://oms/data/DH_ExtSeed_UserPermissionData.xml so they live with the artifact group. -->
    <artifactGroups artifactGroupId="SHOPIFY_POS_API" description="Shopify Embedded App API">
        <artifacts artifactTypeEnumId="AT_REST_PATH" inheritAuthz="Y" artifactName="/app-bridge"/>
        <!-- Full permissions for the ADMIN user group -->
        <authz artifactAuthzId="SHOPIFY_POS_API" userGroupId="ADMIN" authzTypeEnumId="AUTHZT_ALWAYS" authzActionEnumId="AUTHZA_ALL"/>
        <!-- Full permissions for the application user groups -->
        <authz artifactAuthzId="SHOPIFY_POS_API_SM" userGroupId="STORE_MANAGER" authzTypeEnumId="AUTHZT_ALWAYS" authzActionEnumId="AUTHZA_ALL"/>
        <authz artifactAuthzId="SHOPIFY_POS_API_WM" userGroupId="WAREHOUSE_MANAGER" authzTypeEnumId="AUTHZT_ALWAYS" authzActionEnumId="AUTHZA_ALL"/>
        <authz artifactAuthzId="SHOPIFY_POS_API_CSR" userGroupId="CSR" authzTypeEnumId="AUTHZT_ALWAYS" authzActionEnumId="AUTHZA_ALL"/>
        <authz artifactAuthzId="SHOPIFY_POS_API_OM" userGroupId="ORDER_MANAGER" authzTypeEnumId="AUTHZT_ALWAYS" authzActionEnumId="AUTHZA_ALL"/>
        <authz artifactAuthzId="SHOPIFY_POS_API_MM" userGroupId="MERCHANDISE_MGR" authzTypeEnumId="AUTHZT_ALWAYS" authzActionEnumId="AUTHZA_ALL"/>
    </artifactGroups>
</entity-facade-xml>
```

### mantle-shopify-connector
**Release tag:** v4.1.0    **Exact file:** upgrade/v4.1.0/UpgradeSQL.sql    **Type:** SQL

```sql
-- Create SHOPIFY_SHOP_REMOTE table
-- Links a Shopify shop to a SystemMessageRemote with a purpose type identifier,
-- used to resolve the correct remote based on purpose (e.g. default app type).
CREATE TABLE SHOPIFY_SHOP_REMOTE (
    SHOP_ID VARCHAR(40) NOT NULL,
    SYSTEM_MESSAGE_REMOTE_ID VARCHAR(40) NOT NULL,
    PURPOSE_TYPE_ID VARCHAR(40) NOT NULL,
    CREATED_DATE DATETIME,
    COMMENTS VARCHAR(255),
    CONSTRAINT PK_SHOPIFY_SHOP_REMOTE PRIMARY KEY (SHOP_ID, SYSTEM_MESSAGE_REMOTE_ID, PURPOSE_TYPE_ID),
    CONSTRAINT SSR_SMR_REMOTE FOREIGN KEY (SYSTEM_MESSAGE_REMOTE_ID) REFERENCES SYSTEM_MESSAGE_REMOTE (SYSTEM_MESSAGE_REMOTE_ID),
    CONSTRAINT SSR_PURPOSE_TYPE FOREIGN KEY (PURPOSE_TYPE_ID) REFERENCES ENUMERATION (ENUM_ID)
);

-- Create SHOPIFY_INVENTORY_CHANNEL table (issue hotwax/mantle-shopify-connector#465)
-- Maps one OMS facility group's aggregate ATP to one Shopify shop's inventory location.
-- Auto-create-new-entity is disabled on production databases, so this table must be created
-- by running this script BEFORE deploying the release that adds the ShopifyInventoryChannel entity
-- (entity/ShopifyEntities.xml) - see upgrade/v4.1.0/UpgradeSteps.md.
-- LAST_UPDATED_STAMP/CREATED_STAMP are not explicit <field> elements in the entity - Moqui
-- appends them to every entity automatically (EntityDefinition.groovy) unless the entity is
-- declared no-update-stamp="true", which ShopifyInventoryChannel is not.
--
-- Two clauses below exist to match what Moqui itself would create, because a table built by this
-- script and a table built by startup-add-missing must be the same table:
--   * CHARACTER SET utf8 - Moqui's mysql8 conf declares character-set="utf8", so every table it
--     creates is utf8mb3, while MySQL 8+ defaults new tables to utf8mb4. Without this clause the
--     FKs below to Moqui-created SHOPIFY_SHOP and FACILITY_GROUP are rejected with
--     "ERROR 3780 ... are incompatible", and so is the later SHPFY_INV_ADJ_DTL_CHANNEL FK from
--     SHOPIFY_INVENTORY_ADJUSTMENT_DETAIL.
--   * DATETIME(3) on FROM_DATE/THRU_DATE - the mysql8 conf maps Moqui's date-time to DATETIME(3).
--     Plain DATETIME silently truncates the millisecond component that ec.user.nowTimestamp sets
--     on fromDate, which changes effective-date comparisons at sub-second resolution.
-- An instance that already ran an earlier copy of this script has utf8mb4 and/or second-precision
-- columns; ALTER them to match before applying the UpcomingRelease ledger script.
CREATE TABLE SHOPIFY_INVENTORY_CHANNEL (
    INVENTORY_CHANNEL_ID VARCHAR(40) NOT NULL,
    SHOP_ID VARCHAR(40) NOT NULL,
    FACILITY_GROUP_ID VARCHAR(40) NOT NULL,
    SHOPIFY_LOCATION_ID VARCHAR(255) NOT NULL,
    DESCRIPTION VARCHAR(255),
    FROM_DATE DATETIME(3) NOT NULL,
    THRU_DATE DATETIME(3),
    LAST_UPDATED_STAMP DATETIME(3),
    CREATED_STAMP DATETIME(3),
    CONSTRAINT PK_INVENTORY_CHANNEL PRIMARY KEY (INVENTORY_CHANNEL_ID),
    CONSTRAINT INVCHNL_SHOP FOREIGN KEY (SHOP_ID) REFERENCES SHOPIFY_SHOP (SHOP_ID),
    CONSTRAINT INVCHNL_FAC_GROUP FOREIGN KEY (FACILITY_GROUP_ID) REFERENCES FACILITY_GROUP (FACILITY_GROUP_ID)
) CHARACTER SET utf8 COLLATE utf8_general_ci;
CREATE INDEX IDX_INVCHNL_SHOP ON SHOPIFY_INVENTORY_CHANNEL (SHOP_ID);

-- Add hash columns to SHOPIFY_ORDER_HISTORY
-- (docs/shopify-inbound-fulfillment-orders-hash/design.md)
-- TARGET DB: MySQL / MySQL 8. VARCHAR(1023) is what Moqui's text-intermediate maps to there
-- (dictionary default; neither the mysql nor mysql8 database block overrides it). On PostgreSQL
-- text-intermediate maps to TEXT instead, so these statements would need adjusting.
-- add-missing-on-startup is disabled on production/staging, so these columns are not created
-- automatically as they are on local/dev - add them by hand BEFORE updating the instance to the
-- release containing these fields. Fresh installs need nothing: a new table is created from the
-- entity definition with both columns already present.

-- DO NOT pipe this whole file (`mysql < UpgradeSQL.sql`). Statements here are per-release and some
-- will already have been applied on a given instance; MySQL has no ADD/CREATE IF NOT EXISTS for
-- these forms, and a plain pipe aborts on the first error - including the CREATE TABLE statements
-- earlier in this file, which would stop execution before ever reaching the two ALTERs below. Run
-- the statements you need individually, or use `mysql --force`. See UpgradeSteps.md.

-- FULFILLMENT_ORDERS_HASH: the new field this release requires. Listed before LOCATIONS_HASH on
-- purpose, so that if the two are run together the expected LOCATIONS_HASH error cannot prevent this
-- one from being created.
ALTER TABLE SHOPIFY_ORDER_HISTORY ADD COLUMN FULFILLMENT_ORDERS_HASH VARCHAR(1023);

-- LOCATIONS_HASH: pre-existing field (shopify-fulfillment-location-sync) that has no migration SQL
-- anywhere under upgrade/ - included to close that documentation gap and to cover any instance that
-- somehow lacks it. EXPECT THIS TO ERROR on instances where the column already exists, which is the
-- normal case on production (it was created from the entity definition at deploy time, while
-- add-missing was still enabled). That error is safe to skip - the statement above has already run.
ALTER TABLE SHOPIFY_ORDER_HISTORY ADD COLUMN LOCATIONS_HASH VARCHAR(1023);

-- Create outbound return/exchange push-history tables.
-- These entity definitions were added after the Shopify OMS bridge was migrated into this
-- connector. Production and staging disable automatic schema creation, so run these statements
-- before deploying the connector revision that adds the entities to ShopifyHistoryEntities.xml.
CREATE TABLE SHOPIFY_RETURN_PUSH_HISTORY (
    RETURN_ID VARCHAR(40) NOT NULL,
    SHOP_ID VARCHAR(40),
    SHOPIFY_RETURN_ID VARCHAR(255),
    PUSH_STATUS_ID VARCHAR(40),
    PUSH_ERROR_MESSAGE VARCHAR(4095),
    LAST_ATTEMPT_DATE DATETIME(3),
    PROCESSED_DATE DATETIME(3),
    CLOSE_PUSH_STATUS_ID VARCHAR(40),
    CLOSE_PUSH_ERROR_MESSAGE VARCHAR(4095),
    CLOSE_LAST_ATTEMPT_DATE DATETIME(3),
    CLOSE_PROCESSED_DATE DATETIME(3),
    LAST_UPDATED_STAMP DATETIME(3),
    CREATED_STAMP DATETIME(3),
    CONSTRAINT PK_SHPFY_RTN_PUSH_HIST PRIMARY KEY (RETURN_ID),
    CONSTRAINT SRPH_RETURN FOREIGN KEY (RETURN_ID) REFERENCES RETURN_HEADER (RETURN_ID),
    CONSTRAINT SRPH_SHOP FOREIGN KEY (SHOP_ID) REFERENCES SHOPIFY_SHOP (SHOP_ID),
    CONSTRAINT SRPH_PUSH_STATUS FOREIGN KEY (PUSH_STATUS_ID) REFERENCES ENUMERATION (ENUM_ID),
    CONSTRAINT SRPH_CLOSE_STATUS FOREIGN KEY (CLOSE_PUSH_STATUS_ID) REFERENCES ENUMERATION (ENUM_ID)
);
CREATE INDEX SHPFY_RTN_PUSH_STATUS ON SHOPIFY_RETURN_PUSH_HISTORY (PUSH_STATUS_ID);

CREATE TABLE SHOPIFY_EXCHANGE_PUSH_HISTORY (
    RETURN_ID VARCHAR(40) NOT NULL,
    SHOP_ID VARCHAR(40),
    SHOPIFY_RETURN_ID VARCHAR(255),
    PUSH_STATUS_ID VARCHAR(40),
    PUSH_ERROR_MESSAGE VARCHAR(4095),
    LAST_ATTEMPT_DATE DATETIME(3),
    PROCESSED_DATE DATETIME(3),
    PROCESS_STATUS_ID VARCHAR(40),
    PROCESS_ERROR_MESSAGE VARCHAR(4095),
    PROCESS_LAST_ATTEMPT_DATE DATETIME(3),
    PROCESS_PROCESSED_DATE DATETIME(3),
    LAST_UPDATED_STAMP DATETIME(3),
    CREATED_STAMP DATETIME(3),
    CONSTRAINT PK_SHPFY_EXCH_PUSH_HIST PRIMARY KEY (RETURN_ID),
    CONSTRAINT SEPH_RETURN FOREIGN KEY (RETURN_ID) REFERENCES RETURN_HEADER (RETURN_ID),
    CONSTRAINT SEPH_SHOP FOREIGN KEY (SHOP_ID) REFERENCES SHOPIFY_SHOP (SHOP_ID),
    CONSTRAINT SEPH_PUSH_STATUS FOREIGN KEY (PUSH_STATUS_ID) REFERENCES ENUMERATION (ENUM_ID),
    CONSTRAINT SEPH_PROCESS_STATUS FOREIGN KEY (PROCESS_STATUS_ID) REFERENCES ENUMERATION (ENUM_ID)
);
CREATE INDEX SHPFY_EXC_PUSH_STATUS ON SHOPIFY_EXCHANGE_PUSH_HISTORY (PUSH_STATUS_ID);
```

### mantle-shopify-connector
**Release tag:** v4.1.1    **Exact file:** upgrade/v4.1.1/UpgradeData.xml    **Type:** XML

```xml
<?xml version="1.0" encoding="UTF-8"?>
<entity-facade-xml type="ext-upgrade">
    <!-- Add filter parameter key in additionalParameters for queue_ShopifyOrderSync (issue #488) -->
    <moqui.service.job.ServiceJob jobName="queue_ShopifyOrderSync">
        <parameters parameterName="additionalParameters" parameterValue="{&quot;thruDateBuffer&quot;: 1, &quot;filter&quot;: null}"/>
    </moqui.service.job.ServiceJob>
</entity-facade-xml>
```

### mantle-shopify-connector
**Release tag:** v4.1.2    **Exact file:** upgrade/v4.1.2/UpgradeData.xml    **Type:** XML

```xml
<?xml version="1.0" encoding="UTF-8"?>
<entity-facade-xml type="ext-upgrade">
    <!-- Everything that shipped in v4.1.0 is in upgrade/v4.1.0/UpgradeData.xml and is not repeated
         here. This file carries only what the NEXT release adds. -->

    <moqui.basic.StatusType statusTypeId="SHPFY_INV_ADJ_DTL"
            description="Shopify Inventory Adjustment Detail"/>
    <moqui.basic.StatusItem statusId="DETAIL_PENDING" statusTypeId="SHPFY_INV_ADJ_DTL"
            statusCode="PENDING" description="Pending" sequenceNum="1"/>
    <moqui.basic.StatusItem statusId="DETAIL_ASSIGNED" statusTypeId="SHPFY_INV_ADJ_DTL"
            statusCode="ASSIGNED" description="Assigned" sequenceNum="2"/>
    <moqui.basic.StatusItem statusId="DETAIL_NOOP" statusTypeId="SHPFY_INV_ADJ_DTL"
            statusCode="NOOP" description="No Shopify adjustment required" sequenceNum="3"/>
    <moqui.basic.StatusItem statusId="DETAIL_ERROR" statusTypeId="SHPFY_INV_ADJ_DTL"
            statusCode="ERROR" description="Quarantined: malformed group, never batched" sequenceNum="4"/>

    <moqui.service.message.SystemMessageType systemMessageTypeId="ShopifyInventoryAdjustment"
            description="One Shopify aggregate inventory publication batch, sent idempotently or cancelled before delivery"
            sendServiceName="co.hotwax.sob.product.InventoryServices.send#ShopifyInventoryAdjustmentSystemMessage"/>

    <!-- Event Data Documents and feed links for deployed instances. -->
    <dataDocuments dataDocumentId="ShopifyShipmentReceiptEvent" documentName="Shopify Shipment Receipt Event"
            primaryEntityName="org.apache.ofbiz.shipment.receipt.ShipmentReceipt">
        <fields fieldSeqId="01" fieldPath="receiptId"/>
    </dataDocuments>
    <dataDocuments dataDocumentId="ShopifyPhysicalInventoryEvent" documentName="Shopify Physical Inventory Event"
            primaryEntityName="org.apache.ofbiz.product.inventory.PhysicalInventory">
        <fields fieldSeqId="01" fieldPath="physicalInventoryId"/>
    </dataDocuments>
    <dataDocuments dataDocumentId="ShopifyExternalInventoryResetEvent" documentName="Shopify External Inventory Reset Event"
            primaryEntityName="org.apache.ofbiz.product.inventory.ExternalInventoryReset">
        <fields fieldSeqId="01" fieldPath="resetItemId"/>
    </dataDocuments>
    <dataDocuments dataDocumentId="ShopifyPosItemIssuanceEvent" documentName="Shopify POS Item Issuance Event"
            primaryEntityName="org.apache.ofbiz.shipment.issuance.ItemIssuance">
        <fields fieldSeqId="01" fieldPath="itemIssuanceId"/>
        <fields fieldSeqId="02" fieldPath="issuanceTypeId"/>
        <conditions conditionSeqId="01" fieldNameAlias="issuanceTypeId" operator="equals" fieldValue="POS_SALE"/>
    </dataDocuments>
    <dataDocuments dataDocumentId="ShopifyReservationCreatedEvent" documentName="Shopify Reservation Created Event"
            primaryEntityName="org.apache.ofbiz.product.inventory.InventoryItemDetail">
        <fields fieldSeqId="01" fieldPath="inventoryItemId"/>
        <fields fieldSeqId="02" fieldPath="inventoryItemDetailSeqId"/>
        <fields fieldSeqId="03" fieldPath="reasonEnumId"/>
        <conditions conditionSeqId="01" fieldNameAlias="reasonEnumId" operator="equals" fieldValue="INV_RES_CREATE"/>
    </dataDocuments>
    <dataDocuments dataDocumentId="ShopifyReservationReleaseEvent" documentName="Shopify Reservation Release Event"
            primaryEntityName="org.apache.ofbiz.product.inventory.InventoryItemDetail">
        <fields fieldSeqId="01" fieldPath="inventoryItemId"/>
        <fields fieldSeqId="02" fieldPath="inventoryItemDetailSeqId"/>
        <fields fieldSeqId="03" fieldPath="reasonEnumId"/>
        <conditions conditionSeqId="01" fieldNameAlias="reasonEnumId" operator="equals" fieldValue="INV_RES_RELEASE"/>
    </dataDocuments>
    <dataDocuments dataDocumentId="ShopifyProductFacilityAuditEvent" documentName="Shopify Product Facility Audit Event"
            primaryEntityName="moqui.entity.EntityAuditLog">
        <fields fieldSeqId="01" fieldPath="auditHistorySeqId"/>
        <fields fieldSeqId="02" fieldPath="changedEntityName"/>
        <fields fieldSeqId="03" fieldPath="changedFieldName"/>
        <fields fieldSeqId="04" fieldPath="pkPrimaryValue"/>
        <fields fieldSeqId="05" fieldPath="pkSecondaryValue"/>
        <fields fieldSeqId="06" fieldPath="pkRestCombinedValue"/>
        <fields fieldSeqId="07" fieldPath="oldValueText"/>
        <fields fieldSeqId="08" fieldPath="newValueText"/>
        <fields fieldSeqId="09" fieldPath="changedDate"/>
        <fields fieldSeqId="10" fieldPath="changedInVisitId"/>
        <conditions conditionSeqId="01" fieldNameAlias="changedEntityName" operator="equals"
                fieldValue="org.apache.ofbiz.product.facility.ProductFacility"/>
    </dataDocuments>
    <dataDocuments dataDocumentId="ShopifyFacilityGroupMemberEvent" documentName="Shopify Facility Group Member Event"
            primaryEntityName="org.apache.ofbiz.product.facility.FacilityGroupMember">
        <fields fieldSeqId="01" fieldPath="facilityId"/>
        <fields fieldSeqId="02" fieldPath="facilityGroupId"/>
        <fields fieldSeqId="03" fieldPath="fromDate"/>
        <fields fieldSeqId="04" fieldPath="thruDate"/>
    </dataDocuments>
    <dataDocuments dataDocumentId="ShopifyProductStoreFacilityAuditEvent" documentName="Shopify Product Store Facility Audit Event"
            primaryEntityName="moqui.entity.EntityAuditLog">
        <fields fieldSeqId="01" fieldPath="auditHistorySeqId"/>
        <fields fieldSeqId="02" fieldPath="changedEntityName"/>
        <fields fieldSeqId="03" fieldPath="changedFieldName"/>
        <fields fieldSeqId="04" fieldPath="pkPrimaryValue"/>
        <fields fieldSeqId="05" fieldPath="pkSecondaryValue"/>
        <fields fieldSeqId="06" fieldPath="pkRestCombinedValue"/>
        <fields fieldSeqId="07" fieldPath="oldValueText"/>
        <fields fieldSeqId="08" fieldPath="newValueText"/>
        <fields fieldSeqId="09" fieldPath="changedDate"/>
        <fields fieldSeqId="10" fieldPath="changedInVisitId"/>
        <conditions conditionSeqId="01" fieldNameAlias="changedEntityName" operator="equals"
                fieldValue="org.apache.ofbiz.product.store.ProductStoreFacility"/>
    </dataDocuments>
    <dataDocuments dataDocumentId="ShopifyInventoryChannelAuditEvent" documentName="Shopify Inventory Channel Audit Event"
            primaryEntityName="moqui.entity.EntityAuditLog">
        <fields fieldSeqId="01" fieldPath="auditHistorySeqId"/>
        <fields fieldSeqId="02" fieldPath="changedEntityName"/>
        <fields fieldSeqId="03" fieldPath="changedFieldName"/>
        <fields fieldSeqId="04" fieldPath="pkPrimaryValue"/>
        <fields fieldSeqId="05" fieldPath="pkSecondaryValue"/>
        <fields fieldSeqId="06" fieldPath="pkRestCombinedValue"/>
        <fields fieldSeqId="07" fieldPath="oldValueText"/>
        <fields fieldSeqId="08" fieldPath="newValueText"/>
        <fields fieldSeqId="09" fieldPath="changedDate"/>
        <fields fieldSeqId="10" fieldPath="changedInVisitId"/>
        <conditions conditionSeqId="01" fieldNameAlias="changedEntityName" operator="equals"
                fieldValue="co.hotwax.shopify.ShopifyInventoryChannel"/>
    </dataDocuments>

    <co.hotwax.sob.product.InventoryFeedServices.ensure-ShopifyInventoryChannelEventFeed/>
    <moqui.entity.feed.DataFeedDocument dataFeedId="ShopifyInventoryChannelEventFeed" dataDocumentId="ShopifyShipmentReceiptEvent"/>
    <moqui.entity.feed.DataFeedDocument dataFeedId="ShopifyInventoryChannelEventFeed" dataDocumentId="ShopifyPhysicalInventoryEvent"/>
    <moqui.entity.feed.DataFeedDocument dataFeedId="ShopifyInventoryChannelEventFeed" dataDocumentId="ShopifyExternalInventoryResetEvent"/>
    <moqui.entity.feed.DataFeedDocument dataFeedId="ShopifyInventoryChannelEventFeed" dataDocumentId="ShopifyPosItemIssuanceEvent"/>
    <moqui.entity.feed.DataFeedDocument dataFeedId="ShopifyInventoryChannelEventFeed" dataDocumentId="ShopifyReservationCreatedEvent"/>
    <moqui.entity.feed.DataFeedDocument dataFeedId="ShopifyInventoryChannelEventFeed" dataDocumentId="ShopifyReservationReleaseEvent"/>
    <moqui.entity.feed.DataFeedDocument dataFeedId="ShopifyInventoryChannelEventFeed" dataDocumentId="ShopifyProductFacilityAuditEvent"/>
    <moqui.entity.feed.DataFeedDocument dataFeedId="ShopifyInventoryChannelEventFeed" dataDocumentId="ShopifyFacilityGroupMemberEvent"/>
    <moqui.entity.feed.DataFeedDocument dataFeedId="ShopifyInventoryChannelEventFeed" dataDocumentId="ShopifyProductStoreFacilityAuditEvent"/>
    <moqui.entity.feed.DataFeedDocument dataFeedId="ShopifyInventoryChannelEventFeed" dataDocumentId="ShopifyInventoryChannelAuditEvent"/>

    <moqui.service.job.ServiceJob jobName="ShopifyInventoryEffectiveDateEvents"
            description="Dispatch newly effective Shopify InventoryChannel membership boundaries"
            serviceName="co.hotwax.sob.product.InventoryServices.run#ShopifyInventoryEffectiveDateEvents"
            cronExpression="0 0/5 * * * ?" paused="Y">
    </moqui.service.job.ServiceJob>

    <!-- TEMPLATE ONLY - never unpause this row; clone it per inventory channel instead. See UpgradeSteps.md.

         Runs drain#, not publish#. publish# creates at most one System Message per run, so a channel
         drained one message per cron tick and could not keep up: measured on channel CH_ONLINE_10000,
         3242 pending details across 1618 inventory items against a batch of 6. drain# repeats the same
         publish until the channel's queue is empty - one run cleared that whole backlog in 16 passes.

         No migration statement accompanies this. The feature is unreleased, so no instance has a
         per-channel clone on the old service name; every environment receives this row for the first
         time from the seed data. The job NAME stays publish_* because the Company app clones the
         template by that literal name (useShopify.ts EVENT_PUBLISHER_TEMPLATE_JOB) - it names the
         channel's publisher job, not the service that implements it. -->
    <moqui.service.job.ServiceJob jobName="publish_PendingShopifyInventoryAdjustments"
            description="TEMPLATE (clone per inventory channel): keep creating retry-safe Shopify inventory adjustment System Messages until one channel's pending event queue is empty"
            serviceName="co.hotwax.sob.product.InventoryServices.drain#PendingShopifyInventoryAdjustments"
            cronExpression="0 0/5 * * * ?" paused="Y">
        <parameters parameterName="maxChangeCount" parameterValue="100"/>
        <parameters parameterName="staleSendingMinutes" parameterValue="60"/>
        <!-- Matches the ext-seed template and the service default. A pass creates ONE System Message,
             and the default grouping makes one message per (channel, inventory item, event type) - so
             maxPasses is a ceiling on distinct groups in a backlog, not on rows. At 200 a channel with
             more groups than that stops on pass-ceiling and leaves the rest queued for the next cron
             tick; the 1,618-item backlog in the docs would need at least 1,618. Upgraded installs were
             getting a different ceiling from fresh ones for no reason. -->
        <parameters parameterName="maxPasses" parameterValue="5000"/>
    </moqui.service.job.ServiceJob>

    <moqui.service.job.ServiceJob jobName="purge_OldShopifyInventoryAdjustmentDetails_hourly"
            description="Purge terminal Shopify inventory adjustment details beyond the retention window"
            serviceName="co.hotwax.sob.product.InventoryServices.purge#OldShopifyInventoryAdjustmentDetails"
            cronExpression="0 0 * * * ?" paused="N">
        <parameters parameterName="daysToKeep" parameterValue="5"/>
        <parameters parameterName="purgeUnsynced" parameterValue="false"/>
    </moqui.service.job.ServiceJob>

    <!-- The closed event-type vocabulary, repeated verbatim from
         data/DB_ExtSeed_ShopifyInventoryAdjustmentData.xml - keep the two in step.

         These MUST be here and not only in the ext-seed file. An upgrade loads this file and
         nothing else (maarg-util UpgradeDataServices.runComponentUpgrade reads
         upgrade/<version>/UpgradeData.xml per component; it never loads data/*_ExtSeed_*.xml),
         and the ext-seed path only runs on a fresh install. Leaving them out means an upgraded
         instance auto-creates SHOPIFY_INVENTORY_EVENT_TYPE empty while
         SHOPIFY_INVENTORY_ADJUSTMENT_DETAIL.EVENT_TYPE_ID is foreign-keyed to it - so every event
         write is rejected by the database rather than merely losing a label. The INSERT in
         UpgradeSQL.sql does not cover this case either: that block is only run when automatic
         entity creation is disabled.

         Loading them twice is harmless - a data load asserts rows, it does not duplicate them. -->
    <co.hotwax.shopify.ShopifyInventoryEventType eventTypeId="RECEIPT" sequenceNum="1"
            description="Inbound shipment receipt (non-transfer)" shopifyReason="received"/>
    <co.hotwax.shopify.ShopifyInventoryEventType eventTypeId="TRANSFER_RECEIPT" sequenceNum="2"
            description="Transfer order shipment receipt" shopifyReason="movement_received"/>
    <co.hotwax.shopify.ShopifyInventoryEventType eventTypeId="RETURN_RESTOCK" sequenceNum="3"
            description="Customer return restocked to available" shopifyReason="restock"/>
    <co.hotwax.shopify.ShopifyInventoryEventType eventTypeId="PHYSICAL_INVENTORY" sequenceNum="4"
            description="Physical inventory variance" shopifyReason="cycle_count_available"/>
    <co.hotwax.shopify.ShopifyInventoryEventType eventTypeId="CYCLE_COUNT" sequenceNum="5"
            description="Cycle count variance" shopifyReason="cycle_count_available"/>
    <co.hotwax.shopify.ShopifyInventoryEventType eventTypeId="POS_ISSUANCE" sequenceNum="6"
            description="POS sale issuance" shopifyReason="correction"/>
    <co.hotwax.shopify.ShopifyInventoryEventType eventTypeId="EXTERNAL_RESET" sequenceNum="7"
            description="External inventory reset" shopifyReason="correction"/>
    <!-- RESERVATION_* are deliberately unmapped: reservation_created/reservation_deleted describe
         Shopify's `reserved` state and this pipeline adjusts `available`. Null falls back to
         `correction`, which is never false. -->
    <co.hotwax.shopify.ShopifyInventoryEventType eventTypeId="RESERVATION_CREATE" sequenceNum="8"
            description="Inventory reservation created (reason unmapped, publishes as correction)"/>
    <co.hotwax.shopify.ShopifyInventoryEventType eventTypeId="RESERVATION_RELEASE" sequenceNum="9"
            description="Inventory reservation released (reason unmapped, publishes as correction)"/>
    <co.hotwax.shopify.ShopifyInventoryEventType eventTypeId="PRODUCT_FACILITY_CONFIG" sequenceNum="10"
            description="ProductFacility brokering/safety-stock change" shopifyReason="correction"/>
    <co.hotwax.shopify.ShopifyInventoryEventType eventTypeId="PRODUCT_STORE_FACILITY" sequenceNum="11"
            description="ProductStoreFacility effective-date boundary" shopifyReason="correction"/>
    <co.hotwax.shopify.ShopifyInventoryEventType eventTypeId="PRODUCT_STORE_FACILITY_AUDIT" sequenceNum="12"
            description="ProductStoreFacility row edit (audit)" shopifyReason="correction"/>
    <co.hotwax.shopify.ShopifyInventoryEventType eventTypeId="FACILITY_GROUP_MEMBER" sequenceNum="13"
            description="Facility group membership effective-date boundary" shopifyReason="correction"/>
    <co.hotwax.shopify.ShopifyInventoryEventType eventTypeId="INVENTORY_CHANNEL" sequenceNum="14"
            description="Inventory channel effective-date boundary" shopifyReason="correction"/>
    <co.hotwax.shopify.ShopifyInventoryEventType eventTypeId="INVENTORY_CHANNEL_AUDIT" sequenceNum="15"
            description="Inventory channel row edit / retarget (audit)" shopifyReason="correction"/>
</entity-facade-xml>
```

### mantle-shopify-connector
**Release tag:** v4.1.2    **Exact file:** upgrade/v4.1.2/UpgradeSQL.sql    **Type:** SQL

```sql
-- Upgrade SQL for the NEXT release. Everything that shipped in v4.1.0, including
-- CREATE TABLE SHOPIFY_INVENTORY_CHANNEL, is in upgrade/v4.1.0/UpgradeSQL.sql and is not repeated
-- here - an instance coming from v4.1.0 already has it.
--
-- DO NOT pipe this whole file (`mysql < UpgradeSQL.sql`). MySQL has no ADD/CREATE IF NOT EXISTS for
-- these forms and a plain pipe aborts on the first error, so a statement already applied on a given
-- instance stops everything after it. Run the statements you need individually, or use
-- `mysql --force`. See UpgradeSteps.md.

-- Create the event type reference table, the closed vocabulary of OMS event kinds the ledger records
-- and the Shopify adjustment reason each one publishes under. It must exist and be populated BEFORE
-- SHOPIFY_INVENTORY_ADJUSTMENT_DETAIL, whose EVENT_TYPE_ID is foreign-keyed to it - an unseeded type
-- is not a missing label, it is a failed insert on the event that would have used it.
-- SHOPIFY_REASON is validated server-side by inventoryAdjustQuantities against a fixed enumeration and
-- an invalid value fails the WHOLE mutation, so it lives in a row rather than in code: a wrong value
-- is fixed by editing this table and the next batch picks it up, instead of by shipping a release.
-- A NULL SHOPIFY_REASON means "not mapped, publish under correction" and is a decision, not a gap.
-- These rows are also asserted on every data load from
-- data/DB_ExtSeed_ShopifyInventoryAdjustmentData.xml - keep the two in step.
--
-- The explicit CHARACTER SET is required, not decorative. Moqui's mysql8 database conf declares
-- character-set="utf8" collate="utf8_general_ci", so every table Moqui creates is utf8mb3, while
-- MySQL 8+ defaults the server and schema to utf8mb4. Without this clause a hand-run of this
-- script inherits utf8mb4 and the SHOPIFY_INVENTORY_ADJUSTMENT_DETAIL foreign keys below - which
-- reference Moqui-created SHOPIFY_INVENTORY_CHANNEL, SYSTEM_MESSAGE and STATUS_ITEM - are
-- rejected with "ERROR 3780 ... are incompatible", leaving a half-applied schema. Dev instances
-- never catch this because startup-add-missing=true means Moqui creates the tables itself.
CREATE TABLE SHOPIFY_INVENTORY_EVENT_TYPE (
    EVENT_TYPE_ID VARCHAR(40) NOT NULL,
    DESCRIPTION VARCHAR(255),
    SHOPIFY_REASON VARCHAR(63),
    SEQUENCE_NUM DECIMAL(20,0),
    LAST_UPDATED_STAMP DATETIME(3),
    CREATED_STAMP DATETIME(3),
    CONSTRAINT PK_SHPFY_INV_EVENT_TYPE PRIMARY KEY (EVENT_TYPE_ID)
) CHARACTER SET utf8 COLLATE utf8_general_ci;
INSERT INTO SHOPIFY_INVENTORY_EVENT_TYPE (EVENT_TYPE_ID, DESCRIPTION, SHOPIFY_REASON, SEQUENCE_NUM) VALUES
    ('RECEIPT',                      'Inbound shipment receipt (non-transfer)',                                  'received',              1),
    ('TRANSFER_RECEIPT',             'Transfer order shipment receipt',                                           'movement_received',     2),
    ('RETURN_RESTOCK',               'Customer return restocked to available',                                    'restock',               3),
    ('PHYSICAL_INVENTORY',           'Physical inventory variance',                                               'cycle_count_available', 4),
    ('CYCLE_COUNT',                  'Cycle count variance',                                                      'cycle_count_available', 5),
    ('POS_ISSUANCE',                 'POS sale issuance',                                                         'correction',            6),
    ('EXTERNAL_RESET',               'External inventory reset',                                                  'correction',            7),
    ('RESERVATION_CREATE',           'Inventory reservation created (reason unmapped, publishes as correction)',  NULL,                    8),
    ('RESERVATION_RELEASE',          'Inventory reservation released (reason unmapped, publishes as correction)', NULL,                    9),
    ('PRODUCT_FACILITY_CONFIG',      'ProductFacility brokering/safety-stock change',                             'correction',           10),
    ('PRODUCT_STORE_FACILITY',       'ProductStoreFacility effective-date boundary',                              'correction',           11),
    ('PRODUCT_STORE_FACILITY_AUDIT', 'ProductStoreFacility row edit (audit)',                                     'correction',           12),
    ('FACILITY_GROUP_MEMBER',        'Facility group membership effective-date boundary',                         'correction',           13),
    ('INVENTORY_CHANNEL',            'Inventory channel effective-date boundary',                                 'correction',           14),
    ('INVENTORY_CHANNEL_AUDIT',      'Inventory channel row edit / retarget (audit)',                             'correction',           15);

-- Create the immutable inventory-event write-ahead ledger used by aggregate Shopify adjustments.
-- The key is (EVENT_TYPE_ID, EVENT_REFERENCE_ID, INVENTORY_CHANNEL_ID, SHOPIFY_INVENTORY_ITEM_ID).
-- The type names WHAT KIND of source event this row came from and the reference names WHICH
-- occurrence of it - they are two columns rather than one packed string because the type is the
-- thing that has to be joinable to a reason and queryable on its own. The channel pins one shop and
-- one aggregate location, and the inventory item is the remote target within it, so one row is
-- exactly one (inventoryItemId, locationId) change entry. There is no PRODUCT_ID or
-- SHOPIFY_PRODUCT_ID column - a row names a Shopify target and a delta, and the OMS product is
-- recovered by joining SHOPIFY_SHOP_PRODUCT on the channel's shop and this inventory item.
-- Both id-long columns keep the full VARCHAR(255) that Moqui's id-long implies, which the key sizes
-- allow against MySQL 8's 3072-byte InnoDB limit at either width. This table is created utf8mb3 to
-- match Moqui (see the CHARACTER SET note on SHOPIFY_INVENTORY_EVENT_TYPE above), so the primary key
-- is 120 + 765 + 120 + 765 = 1770 bytes and SHPFY_INV_ADJ_DTL_TARGET is 1245; even if a future
-- Moqui conf moves to utf8mb4 they would be 2360 and 1660, still inside the limit.
CREATE TABLE SHOPIFY_INVENTORY_ADJUSTMENT_DETAIL (
    EVENT_TYPE_ID VARCHAR(40) NOT NULL,
    EVENT_REFERENCE_ID VARCHAR(255) NOT NULL,
    INVENTORY_CHANNEL_ID VARCHAR(40) NOT NULL,
    SHOPIFY_INVENTORY_ITEM_ID VARCHAR(255) NOT NULL,
    -- Null for almost every row: the channel's current location is the target. Set only on a delta
    -- that clears a location the channel has stopped pointing at, which cannot be resolved through
    -- the channel because the channel has already moved. Not in the primary key - a row is still one
    -- (event, channel, inventory item) - and not indexed, because it is only ever read alongside
    -- SHOPIFY_INVENTORY_ITEM_ID on rows the SHPFY_INV_ADJ_DTL_TARGET index has already narrowed.
    PUBLISH_SHOPIFY_LOCATION_ID VARCHAR(255),
    COMPUTED_INVENTORY_CHANGE DECIMAL(26,6) NOT NULL,
    DECISION_COMMENT VARCHAR(1023) NOT NULL,
    SYSTEM_MESSAGE_ID VARCHAR(40),
    DETAIL_STATUS_ID VARCHAR(40) NOT NULL,
    CREATED_DATE DATETIME(3) NOT NULL,
    LAST_UPDATED_STAMP DATETIME(3),
    CREATED_STAMP DATETIME(3),
    CONSTRAINT PK_SHPFY_INV_ADJ_DETAIL PRIMARY KEY
        (EVENT_TYPE_ID, EVENT_REFERENCE_ID, INVENTORY_CHANNEL_ID, SHOPIFY_INVENTORY_ITEM_ID),
    CONSTRAINT SHPFY_INV_ADJ_DTL_CHANNEL FOREIGN KEY (INVENTORY_CHANNEL_ID) REFERENCES SHOPIFY_INVENTORY_CHANNEL (INVENTORY_CHANNEL_ID),
    CONSTRAINT SHPFY_INV_ADJ_DTL_EVT_TYPE FOREIGN KEY (EVENT_TYPE_ID) REFERENCES SHOPIFY_INVENTORY_EVENT_TYPE (EVENT_TYPE_ID),
    CONSTRAINT SHPFY_INV_ADJ_DTL_MESSAGE FOREIGN KEY (SYSTEM_MESSAGE_ID) REFERENCES SYSTEM_MESSAGE (SYSTEM_MESSAGE_ID),
    CONSTRAINT SHPFY_INV_ADJ_DTL_STATUS FOREIGN KEY (DETAIL_STATUS_ID) REFERENCES STATUS_ITEM (STATUS_ID)
) CHARACTER SET utf8 COLLATE utf8_general_ci;
-- EVENT_TYPE_ID is the last column of the claim index because eventTypeId is part of the batcher's
-- default grouping and a claim filters on every grouping field.
CREATE INDEX SHPFY_INV_ADJ_DTL_TARGET ON SHOPIFY_INVENTORY_ADJUSTMENT_DETAIL
    (INVENTORY_CHANNEL_ID, DETAIL_STATUS_ID, SYSTEM_MESSAGE_ID, SHOPIFY_INVENTORY_ITEM_ID, EVENT_TYPE_ID);
CREATE INDEX SHPFY_INV_ADJ_DTL_MSG ON SHOPIFY_INVENTORY_ADJUSTMENT_DETAIL (SYSTEM_MESSAGE_ID);
CREATE INDEX SHPFY_INV_ADJ_DTL_PURGE ON SHOPIFY_INVENTORY_ADJUSTMENT_DETAIL
    (DETAIL_STATUS_ID, CREATED_DATE, SYSTEM_MESSAGE_ID);
CREATE INDEX SHPFY_INV_ADJ_DTL_AGE ON SHOPIFY_INVENTORY_ADJUSTMENT_DETAIL (CREATED_DATE);

-- THERE IS NO MIGRATION FOR AN EXISTING LEDGER HERE, AND THAT IS DELIBERATE. This feature has never
-- been released. Every environment creates both tables above for the first time, already in their
-- final shape, so there is no prior state to migrate from and nothing to clean up: no DataDocument
-- to drop, no stale field alias to clear, no ALTER path to run. Statements for any of those would be
-- a migration for a schema no deployment has ever had. The read projection over this ledger is the
-- view entity co.hotwax.shopify.ShopifyInventoryAdjustmentDetailView, behind
-- GET sob/shopify/inventoryAdjustmentDetails - versioned and deployed with the code that uses it,
-- so a mismatch is a startup error rather than a per-environment runtime failure.

-- Retire the SHOPIFY_INVENTORY_CHANNEL DataDocument. UNLIKE the ledger above, this one HAS been
-- deployed, so removing its definition from the component is not enough: an ext-seed load never
-- deletes rows, so the DATA_DOCUMENT and DATA_DOCUMENT_FIELD rows survive in every environment that
-- ever loaded them, and a document whose primaryEntityName no longer resolves breaks
-- POST oms/dataDocumentView for that document.
--
-- The read it served is now GET sob/shopify/inventoryChannels, over the same entity, versioned and
-- deployed with the code. Repoint any remaining dataDocumentView caller at that endpoint BEFORE
-- running these. Child-to-parent order; run them individually, not as a pipe (see the note above).
DELETE FROM DATA_FEED_DOCUMENT WHERE DATA_DOCUMENT_ID = 'SHOPIFY_INVENTORY_CHANNEL';
DELETE FROM DATA_DOCUMENT_FIELD WHERE DATA_DOCUMENT_ID = 'SHOPIFY_INVENTORY_CHANNEL';
DELETE FROM DATA_DOCUMENT WHERE DATA_DOCUMENT_ID = 'SHOPIFY_INVENTORY_CHANNEL';
-- DATA_DOCUMENT_CONDITION, DATA_DOCUMENT_LINK, DATA_DOCUMENT_REL_ALIAS and DATA_DOCUMENT_USER_GROUP
-- are not listed because this document never seeded any: it was defined with fields only. Add the
-- matching deletes first if an environment turns out to carry rows in them.
```

### mantle-shopify-connector
**Release tag:** v4.1.3    **Exact file:** upgrade/v4.1.3/UpgradeData.xml    **Type:** XML

```xml
<?xml version="1.0" encoding="UTF-8"?>
<entity-facade-xml type="ext-upgrade">
</entity-facade-xml>
```

### mantle-shopify-connector
**Release tag:** v4.1.4    **Exact file:** upgrade/v4.1.4/UpgradeData.xml    **Type:** XML

```xml
<?xml version="1.0" encoding="UTF-8"?>
<entity-facade-xml type="ext-upgrade">
</entity-facade-xml>
```

### mantle-shopify-connector
**Release tag:** v4.1.5    **Exact file:** upgrade/v4.1.5/UpgradeData.xml    **Type:** XML

```xml
<?xml version="1.0" encoding="UTF-8"?>
<entity-facade-xml type="ext-upgrade">
</entity-facade-xml>
```

### mantle-shopify-connector
**Release tag:** v4.1.6    **Exact file:** upgrade/v4.1.6/UpgradeData.xml    **Type:** XML

```xml
<?xml version="1.0" encoding="UTF-8"?>
<entity-facade-xml type="ext-upgrade">
</entity-facade-xml>
```

### mantle-shopify-connector
**Release tag:** v4.1.7    **Exact file:** upgrade/v4.1.7/UpgradeData.xml    **Type:** XML

```xml
<?xml version="1.0" encoding="UTF-8"?>
<entity-facade-xml type="ext-upgrade">
    <!-- Recovery path for Shopify fulfillments the real-time sync missed.

         post#ShopifyFulfillment runs as an async call off the SalesOrderShipmentShipped SECA, so a shipment
         can ship without a CreateShopifyFulfillment SystemMessage ever being produced, and nothing durable
         records the miss - the async task holds no state, and purge#OldSystemMessages removes messages and
         their error rows after 30 days regardless of status. Shipment.externalId is the only lasting signal,
         so the sweep treats its absence as the symptom and replays those shipments through MDM, where a
         replay that still fails gets a row in an error file instead of a swallowed log line.

         Re-seeding POST_SHOPIFY_FULFILLMENT updates the existing row in place (configId is the PK) for
         instances where it was already created by hand.

         The job ships paused; enable sweep_MissedShopifyFulfillments per instance. -->
    <co.hotwax.datamanager.DataManagerConfig configId="POST_SHOPIFY_FULFILLMENT"
        importServiceName="co.hotwax.sob.fulfillment.FulfillmentFeedServices.post#ShopifyFulfillment"
        description="Posts shipment fulfillments to Shopify"
        executionModeId="DMC_QUEUE"/>

    <moqui.basic.Enumeration enumId="SWP_MISSED_FUL" enumCode="SWP_MISSED_FUL"
        description="Sweep Missed Shopify Fulfillments" enumTypeId="FULFILLMENT_SYS_JOB"/>
    <moqui.service.job.ServiceJob jobName="sweep_MissedShopifyFulfillments" jobTypeEnumId="SWP_MISSED_FUL"
        description="Sweep Missed Shopify Fulfillments"
        serviceName="co.hotwax.sob.fulfillment.FulfillmentSweepServices.sweep#MissedShopifyFulfillments"
        cronExpression="0 30 * * * ?" paused="Y">
        <parameters parameterName="configId" parameterValue="POST_SHOPIFY_FULFILLMENT"/>
        <parameters parameterName="lookbackDays" parameterValue="2"/><!-- widen for a one-off backfill -->
        <parameters parameterName="shopId" parameterValue=""/><!-- empty sweeps all shops -->
        <parameters parameterName="shipmentId" parameterValue=""/><!-- set only to pin an ad-hoc run to one shipment -->
        <parameters parameterName="orderId" parameterValue=""/><!-- set only to pin an ad-hoc run to one order -->
    </moqui.service.job.ServiceJob>
</entity-facade-xml>
```

### mantle-shopify-connector
**Release tag:** v4.1.8    **Exact file:** upgrade/v4.1.8/UpgradeData.xml    **Type:** XML

```xml
<?xml version="1.0" encoding="UTF-8"?>
<entity-facade-xml type="ext-upgrade">
</entity-facade-xml>
```

### mantle-shopify-connector
**Release tag:** v4.1.9    **Exact file:** upgrade/v4.1.9/UpgradeData.xml    **Type:** XML

```xml
<?xml version="1.0" encoding="UTF-8"?>
<entity-facade-xml type="ext-upgrade">
    <!-- Return Lifecycle App Mapping Enumeration and Upgrade Mapping -->
    <moqui.basic.Enumeration enumId="RETURN_LIFE_CYCLE" enumTypeId="SHOPIFY_TYPE" description="Return Lifecycle App Mapping"/>

    <!-- Adds the "excludeStatus" parameter to shops that are already set up, so upgrading also starts
         excluding archived products for them. -->
    <moqui.service.job.ServiceJobParameter jobName="sync_ShopifyProductUpdates" parameterName="excludeStatus" parameterValue="archived"/>
      <!-- Add the systemMessageRemoteId for ShopifyShop resolution to avoid multiple SMR conflicts happening due to domain resolution -->

    <!-- Return Lifecycle App Mapping Enumeration and Upgrade Mapping -->
    <moqui.basic.Enumeration enumId="RETURN_LIFE_CYCLE" enumTypeId="SHOP_TYPE_ENUM" description="Return Lifecycle App Mapping"/>

    <moqui.basic.Enumeration enumId="NATIV_BOPIS_PICK_TAG" enumTypeId="PROD_STR_STNG"
            enumName="Native BOPIS pickup tag" description="Shopify order tag for native store pickup orders"/>
    <moqui.basic.Enumeration enumId="NATIV_BOPIS_SHIP_TAG" enumTypeId="PROD_STR_STNG"
            enumName="Native BOPIS ship-to-me tag" description="Shopify order tag for native ship-to-me orders"/>
    <moqui.basic.Enumeration enumId="NATIV_BOPIS_SHIP_MTH" enumTypeId="PROD_STR_STNG"
            enumName="Native BOPIS ship-to-me method" description="OMS shipment method for native ship-to-me orders"/>
    <moqui.basic.Enumeration enumId="NATIV_BOPIS_WH_FAC" enumTypeId="PROD_STR_STNG"
            enumName="Native BOPIS warehouse facility" description="OMS warehouse used when a native BOPIS Shopify location maps to _NA_"/>

    <org.apache.ofbiz.product.store.ProductStoreSetting productStoreId="STORE" settingTypeEnumId="NATIV_BOPIS_PICK_TAG" settingValue="self-service:pick-up"/>
    <org.apache.ofbiz.product.store.ProductStoreSetting productStoreId="STORE" settingTypeEnumId="NATIV_BOPIS_SHIP_TAG" settingValue="self-service:ship-to-me"/>
    <org.apache.ofbiz.product.store.ProductStoreSetting productStoreId="STORE" settingTypeEnumId="NATIV_BOPIS_SHIP_MTH" settingValue="FRE_2_DAY_SHP"/>
    <org.apache.ofbiz.product.store.ProductStoreSetting productStoreId="STORE" settingTypeEnumId="NATIV_BOPIS_WH_FAC" settingValue="WH"/>
</entity-facade-xml>
```

### mantle-shopify-connector
**Release tag:** v4.1.10    **Exact file:** upgrade/v4.1.10/UpgradeData.xml    **Type:** XML

```xml
<?xml version="1.0" encoding="UTF-8"?>
<entity-facade-xml type="ext-upgrade">
</entity-facade-xml>
```

### mantle-shopify-connector
**Release tag:** v4.1.11    **Exact file:** upgrade/v4.1.11/UpgradeData.xml    **Type:** XML

```xml
<?xml version="1.0" encoding="UTF-8"?>
<entity-facade-xml type="ext-upgrade">
</entity-facade-xml>
```

### oms
**Release tag:** v3.0.0-RC1    **Exact file:** upgrade/v3.0.0-RC1/UpgradeData.xml    **Type:** XML

```xml
<?xml version="1.0" encoding="UTF-8"?>
<entity-facade-xml type="ext-upgrade">
    <!-- Canonical OMS order-hold vocabulary. Enumeration IDs are globally keyed, so these records also
         reclassify values previously seeded as standalone types or ORDER_HOLD_PURPOSE values. -->
    <moqui.basic.Enumeration enumId="RESOLVE_ONHOLD_ORDER" enumTypeId="WorkEffortType" description="Resolve On-Hold Order"/>
    <moqui.basic.EnumerationType enumTypeId="RESOLVE_ONHOLD_ORDER" parentTypeId="WorkEffortPurposeType" description="Resolve on Hold Orders"/>
    <moqui.basic.Enumeration enumId="INVALID_ADDRESS" enumTypeId="RESOLVE_ONHOLD_ORDER" description="Invalid Address"/>
    <moqui.basic.Enumeration enumId="NEG_RES_REVIEW" enumTypeId="RESOLVE_ONHOLD_ORDER" description="Review order items with negative inventory reservations and correct reservation records."/>
    <moqui.basic.Enumeration enumId="REVIEW_RISK_ORDER" enumTypeId="RESOLVE_ONHOLD_ORDER" description="Review High-Risk Order"/>
    <moqui.basic.Enumeration enumId="ORD_HOLD_CUST_REQ" enumTypeId="RESOLVE_ONHOLD_ORDER" description="Customer request" sequenceNum="2"/>
    <moqui.basic.Enumeration enumId="ORD_HOLD_MANUAL" enumTypeId="RESOLVE_ONHOLD_ORDER" description="Manual" sequenceNum="3"/>

    <!-- Cancellation transitions for the Transfer Order item status flows so explicit ITEM_CANCELLED requests
        (e.g. cancel#TransferOrder) pass the per-flow validation now done in change#OrderItemStatus.
        conditionExpression="directStatusChange == false" (same convention as the Default flow) keeps services that
        compute the next item status from ever auto-picking these edges. -->
    <moqui.basic.StatusFlowTransition statusFlowId="TO_Fulfill_Only" statusId="ITEM_CREATED" toStatusId="ITEM_CANCELLED" transitionSequence="2" transitionName="Cancel Item" conditionExpression="directStatusChange == false"/>
    <moqui.basic.StatusFlowTransition statusFlowId="TO_Receive_Only" statusId="ITEM_CREATED" toStatusId="ITEM_CANCELLED" transitionSequence="2" transitionName="Cancel Item" conditionExpression="directStatusChange == false"/>
    <moqui.basic.StatusFlowTransition statusFlowId="TO_Receive_Only" statusId="ITEM_PENDING_RECEIPT" toStatusId="ITEM_CANCELLED" transitionSequence="2" transitionName="Cancel Item" conditionExpression="directStatusChange == false"/>
    <moqui.basic.StatusFlowTransition statusFlowId="TO_Fulfill_And_Receive" statusId="ITEM_CREATED" toStatusId="ITEM_CANCELLED" transitionSequence="2" transitionName="Cancel Item" conditionExpression="directStatusChange == false"/>
    <moqui.basic.StatusFlowTransition statusFlowId="TO_Fulfill_And_Receive" statusId="ITEM_PENDING_RECEIPT" toStatusId="ITEM_CANCELLED" transitionSequence="2" transitionName="Cancel Item" conditionExpression="directStatusChange == false"/>

    <moqui.basic.Enumeration description="User Access" enumId="UgtUserAccess" enumTypeId="UserGroupType"/>

    <moqui.security.UserGroup userGroupId="ADMIN" groupTypeEnumId="UgtUserAccess"/>
    <moqui.security.UserGroup userGroupId="CSR" description="Customer Service Representatives" groupTypeEnumId="UgtUserAccess"/>
    <moqui.security.UserGroup userGroupId="STORE_MANAGER" description="Store Managers" groupTypeEnumId="UgtUserAccess"/>
    <moqui.security.UserGroup userGroupId="ORDER_MANAGER" description="Order Managers" groupTypeEnumId="UgtUserAccess"/>
    <moqui.security.UserGroup userGroupId="WAREHOUSE_MANAGER" description="Warehouse Managers" groupTypeEnumId="UgtUserAccess"/>
    <moqui.security.UserGroup userGroupId="MERCHANDISE_MGR" description="Merchandise Managers" groupTypeEnumId="UgtUserAccess"/>

    <!-- =====================PWA App UserPermission ===================== -->
    <moqui.security.UserPermission userPermissionId="BOPIS_APP_VIEW" description="View BOPIS App"/>
    <moqui.security.UserPermission userPermissionId="FULFILLMENT_APP_VIEW" description="View Fulfillment App"/>
    <moqui.security.UserPermission userPermissionId="FULFILLMENT_LEGACY_APP_VIEW" description="View Fulfillment Legacy App"/>
    <moqui.security.UserPermission userPermissionId="INVCOUNT_APP_VIEW" description="View Inventory Count App"/>
    <moqui.security.UserPermission userPermissionId="JOB_MANAGER_APP_VIEW" description="View Job Manager App"/>
    <moqui.security.UserPermission userPermissionId="RECEIVING_APP_VIEW" description="View Receiving App"/>
    <moqui.security.UserPermission userPermissionId="ORDER_ROUTING_APP_VIEW" description="View ATP App"/>
    <moqui.security.UserPermission userPermissionId="COMPANY_APP_VIEW" description="View Company App"/>
    <moqui.security.UserPermission userPermissionId="TRANSFERS_APP_VIEW" description="View Transfers App"/>
    <moqui.security.UserPermission userPermissionId="PRODUCTS_APP_VIEW" description="View Products App"/>
    <moqui.security.UserPermission userPermissionId="ORD_SALES_ORDER_CNCL" description="View Cancel button"/>
    <moqui.security.UserPermission userPermissionId="BOPIS_REQUEST_TRANSFER_UPDATE" description="Show/toggle the Request Transfer card in BOPIS Settings"/>
    <moqui.security.UserPermission userPermissionId="BOPIS_POD_UPDATE" description="Show/toggle the Proof of Delivery card in BOPIS Settings"/>
    <moqui.security.UserPermission userPermissionId="ORD_TRANSFER_ORDER_VIEW" description="View Transfer Order"/>
    <moqui.security.UserPermission userPermissionId="ORD_TRANSFER_ORDER_ADMIN" description="Transfer Order Admin Permission"/>
    <moqui.security.UserPermission userPermissionId="ORD_TRANSFER_ORDER_CANCEL" description="Cancel and Reject operations in the Storefulfillment Component."/>
    <moqui.security.UserPermission userPermissionId="CARRIER_SETUP_VIEW" description="View Carrier Setup Screens"/>
    <moqui.security.UserPermission userPermissionId="FF_ORDER_LOOKUP_VIEW" description="View Fulfillment Order Lookup"/>
    <moqui.security.UserPermission userPermissionId="FF_INVOICING_STATUS_VIEW" description="View Order Invoicing Status"/>
    <moqui.security.UserPermission userPermissionId="ORDER_SHIPMENT_METHOD_UPDATE" description="Update Order Shipment Method"/>
    <moqui.security.UserPermission userPermissionId="FULFILLMENT_VIEW_ALL_PICKERS" description="View pickers/employees across all facilities, not just the current facility"/>
    <moqui.security.UserPermission userPermissionId="INV_COUNT_VAR_LOG" description="Access the inventory count variance/audit log"/>
    <moqui.security.UserPermission userPermissionId="INV_COUNT_ADMIN" description="User can perform all admin operations of inventory count."/>
    <moqui.security.UserPermission userPermissionId="INV_COUNT_LOCK_RLS" description="User can release the lock of inventory count."/>
    <moqui.security.UserPermission userPermissionId="INV_CNT_VIEW_QOH" description="User can view the QoH in count detail and progress review pages."/>
    <moqui.security.UserPermission userPermissionId="INV_COUNT_SUBMIT" description="User can Submit count from progress review page."/>
    <moqui.security.UserPermission userPermissionId="INV_COUNT_PRE_START" description="User can start count before it's start time."/>
    <moqui.security.UserPermission userPermissionId="PREVIEW_COUNT_ITEM" description="User can see items in cycle count sessions track progress page."/>
    <moqui.security.UserPermission userPermissionId="RECEIVING_ADMIN" description="User can perform all admin operations of receiving."/>
    <moqui.security.UserPermission userPermissionId="USERS_LIST_VIEW" description="View List of Users"/>
    <moqui.security.UserPermission userPermissionId="PARTY_SECURITY_ASSIGNMENT" description="Permission for assigning Super, Security and Tenant Admin security groups."/>
    <moqui.security.UserPermission userPermissionId="COMMON_ADMIN" description="Common - Admin"/>
    <moqui.security.UserPermission userPermissionId="PARTYMGR_ADMIN" description="Party Manager - Admin"/>
    <moqui.security.UserPermission userPermissionId="PARTYMGR_UPDATE" description="Update operations in the Party Manager."/>
    <moqui.security.UserPermission userPermissionId="PARTYMGR_VIEW" description="View operations in the Party Manager."/>
    <moqui.security.UserPermission userPermissionId="PARTYMGR_STS_UPDATE" description="Update party status in the Party Manager."/>
    <moqui.security.UserPermission userPermissionId="PARTYMGR_PCM_CREATE" description="Create party contact mechs in the Party Manager."/>
    <moqui.security.UserPermission userPermissionId="PARTYMGR_PCM_UPDATE" description="Update party contact mechs in the Party Manager."/>
    <moqui.security.UserPermission userPermissionId="PARTYMGR_PCM_DELETE" description="Delete party contact mechs in the Party Manager."/>
    <moqui.security.UserPermission userPermissionId="SECURITY_CREATE" description="Security - Create"/>
    <moqui.security.UserPermission userPermissionId="SECURITY_UPDATE" description="Security - Update"/>
    <moqui.security.UserPermission userPermissionId="SECURITY_VIEW" description="View operations in the Security Management Screens."/>
    <moqui.security.UserPermission userPermissionId="SECURITY_ADMIN" description="ALL operations in the Security Management Screens."/>
    <moqui.security.UserPermission userPermissionId="COMMERCEUSER_VIEW" description="User can manage commerce application."/>
    <moqui.security.UserPermission userPermissionId="PIM_PRODUCT_VIEW" description="View Products"/>
    <moqui.security.UserPermission userPermissionId="PIM_PRODUCT_ADMIN" description="Product Admin Permission"/>
    <moqui.security.UserPermission userPermissionId="PIM_FEATURE_ADMIN" description="Features Admin Permission"/>
    <moqui.security.UserPermission userPermissionId="PIM_PRODUCT_CREATE" description="Create Products"/>
    <moqui.security.UserPermission userPermissionId="PIM_FEATURE_CREATE" description="Create Product Features"/>
    <moqui.security.UserPermission userPermissionId="ORDERMGR_VIEW" description="Order Manager - View"/>
    <moqui.security.UserPermission userPermissionId="ORDERMGR_CREATE" description="Order Manager - Create"/>
    <moqui.security.UserPermission userPermissionId="ORDERMGR_UPDATE" description="Order Manager - Update"/>
    <moqui.security.UserPermission userPermissionId="ORDERMGR_ADMIN" description="Order Manager - Admin"/>
    <moqui.security.UserPermission userPermissionId="ORD_SALES_ORDER_VIEW" description="View Sales Order"/>
    <moqui.security.UserPermission userPermissionId="ORD_SALES_ORDER_CREATE" description="Create Sales Order"/>
    <moqui.security.UserPermission userPermissionId="ORD_SALES_ORDER_ADMIN" description="Sales Order Admin Permission"/>
    <moqui.security.UserPermission userPermissionId="ORD_SALES_ORDER_EDIT" description="View Edit Items"/>
    <moqui.security.UserPermission userPermissionId="ORD_CRT_EVENT_VIEW" description="View Create Event"/>
    <moqui.security.UserPermission userPermissionId="COMM_EVNT_MENU_VIEW" description="View Communication Event"/>
    <moqui.security.UserPermission userPermissionId="RELATNSHIP_CUSTOMER_VIEW" description="View Customer"/>
    <moqui.security.UserPermission userPermissionId="RELATNSHIP_CUSTOMER_CREATE" description="Create Customer"/>
    <moqui.security.UserPermission userPermissionId="RELATNSHIP_CUSTOMER_ADMIN" description="Customer Admin Permission"/>
    <moqui.security.UserPermission userPermissionId="MOVE_SO_ITEM" description="Move Item to a Parking Facility"/>
    <moqui.security.UserPermission userPermissionId="STOREFULFILLMENT_ADMIN" description="Admin operations in the Storefulfillment Component."/>
    <moqui.security.UserPermission userPermissionId="SF_UNLOCK_ORDER" description="Unlock order of store fulfillment"/>
    <moqui.security.UserPermission userPermissionId="TRANSFERS_DISCREPANCY_VIEW" description="Transfers - Discrepancy Report - View"/>
    <moqui.security.UserPermission userPermissionId="TRANSFERS_BULK_CREATE" description="Transfers - Bulk Create"/>
    <moqui.security.UserPermission userPermissionId="ROUTING_TEST_DRIVE_VIEW" description="Enable routing rule test-drive in Order Routing"/>

    <!-- ===================== UserGroupPermission ===================== -->
    <!-- ADMIN -->
    <moqui.security.UserGroupPermission userGroupId="ADMIN" userPermissionId="BOPIS_APP_VIEW" fromDate="0"/>
    <moqui.security.UserGroupPermission userGroupId="ADMIN" userPermissionId="FULFILLMENT_APP_VIEW" fromDate="0"/>
    <moqui.security.UserGroupPermission userGroupId="ADMIN" userPermissionId="INVCOUNT_APP_VIEW" fromDate="0"/>
    <moqui.security.UserGroupPermission userGroupId="ADMIN" userPermissionId="RECEIVING_APP_VIEW" fromDate="0"/>
    <moqui.security.UserGroupPermission userGroupId="ADMIN" userPermissionId="JOB_MANAGER_APP_VIEW" fromDate="0"/>
    <moqui.security.UserGroupPermission userGroupId="ADMIN" userPermissionId="ORDER_ROUTING_APP_VIEW" fromDate="0"/>
    <moqui.security.UserGroupPermission userGroupId="ADMIN" userPermissionId="COMPANY_APP_VIEW" fromDate="0"/>
    <moqui.security.UserGroupPermission userGroupId="ADMIN" userPermissionId="TRANSFERS_APP_VIEW" fromDate="0"/>
    <moqui.security.UserGroupPermission userGroupId="ADMIN" userPermissionId="PRODUCTS_APP_VIEW" fromDate="0"/>
    <moqui.security.UserGroupPermission userGroupId="ADMIN" userPermissionId="COMMERCEUSER_VIEW" fromDate="0"/>
    <moqui.security.UserGroupPermission userGroupId="ADMIN" userPermissionId="COMMON_ADMIN" fromDate="0"/>
    <moqui.security.UserGroupPermission userGroupId="ADMIN" userPermissionId="ORD_SALES_ORDER_CNCL" fromDate="0"/>
    <moqui.security.UserGroupPermission userGroupId="ADMIN" userPermissionId="ORD_TRANSFER_ORDER_ADMIN" fromDate="0"/>
    <moqui.security.UserGroupPermission userGroupId="ADMIN" userPermissionId="ORD_TRANSFER_ORDER_CANCEL" fromDate="0"/>
    <moqui.security.UserGroupPermission userGroupId="ADMIN" userPermissionId="CARRIER_SETUP_VIEW" fromDate="0"/>
    <moqui.security.UserGroupPermission userGroupId="ADMIN" userPermissionId="INV_COUNT_ADMIN" fromDate="0"/>
    <moqui.security.UserGroupPermission userGroupId="ADMIN" userPermissionId="INV_COUNT_LOCK_RLS" fromDate="0"/>
    <moqui.security.UserGroupPermission userGroupId="ADMIN" userPermissionId="INV_CNT_VIEW_QOH" fromDate="0"/>
    <moqui.security.UserGroupPermission userGroupId="ADMIN" userPermissionId="INV_COUNT_SUBMIT" fromDate="0"/>
    <moqui.security.UserGroupPermission userGroupId="ADMIN" userPermissionId="INV_COUNT_PRE_START" fromDate="0"/>
    <moqui.security.UserGroupPermission userGroupId="ADMIN" userPermissionId="PREVIEW_COUNT_ITEM" fromDate="0"/>
    <moqui.security.UserGroupPermission userGroupId="ADMIN" userPermissionId="RECEIVING_ADMIN" fromDate="0"/>
    <moqui.security.UserGroupPermission userGroupId="ADMIN" userPermissionId="USERS_LIST_VIEW" fromDate="0"/>
    <moqui.security.UserGroupPermission userGroupId="ADMIN" userPermissionId="PARTY_SECURITY_ASSIGNMENT" fromDate="0"/>
    <moqui.security.UserGroupPermission userGroupId="ADMIN" userPermissionId="PIM_FEATURE_ADMIN" fromDate="0"/>
    <moqui.security.UserGroupPermission userGroupId="ADMIN" userPermissionId="PIM_PRODUCT_ADMIN" fromDate="0"/>
    <moqui.security.UserGroupPermission userGroupId="ADMIN" userPermissionId="PARTYMGR_ADMIN" fromDate="0"/>
    <moqui.security.UserGroupPermission userGroupId="ADMIN" userPermissionId="PARTYMGR_STS_UPDATE" fromDate="0"/>
    <moqui.security.UserGroupPermission userGroupId="ADMIN" userPermissionId="SECURITY_CREATE" fromDate="0"/>
    <moqui.security.UserGroupPermission userGroupId="ADMIN" userPermissionId="SECURITY_UPDATE" fromDate="0"/>
    <moqui.security.UserGroupPermission userGroupId="ADMIN" userPermissionId="ORDER_SHIPMENT_METHOD_UPDATE" fromDate="0"/>
    <moqui.security.UserGroupPermission userGroupId="ADMIN" userPermissionId="STOREFULFILLMENT_ADMIN" fromDate="0"/>
    <moqui.security.UserGroupPermission userGroupId="ADMIN" userPermissionId="SF_UNLOCK_ORDER" fromDate="0"/>
    <moqui.security.UserGroupPermission userGroupId="ADMIN" userPermissionId="ORDERMGR_ADMIN" fromDate="0"/>
    <moqui.security.UserGroupPermission userGroupId="ADMIN" userPermissionId="ORD_CRT_EVENT_VIEW" fromDate="0"/>
    <moqui.security.UserGroupPermission userGroupId="ADMIN" userPermissionId="ORD_SALES_ORDER_ADMIN" fromDate="0"/>
    <moqui.security.UserGroupPermission userGroupId="ADMIN" userPermissionId="ORD_SALES_ORDER_EDIT" fromDate="0"/>
    <moqui.security.UserGroupPermission userGroupId="ADMIN" userPermissionId="COMM_EVNT_MENU_VIEW" fromDate="0"/>
    <moqui.security.UserGroupPermission userGroupId="ADMIN" userPermissionId="RELATNSHIP_CUSTOMER_ADMIN" fromDate="0"/>
    <moqui.security.UserGroupPermission userGroupId="ADMIN" userPermissionId="MOVE_SO_ITEM" fromDate="0"/>
    <moqui.security.UserGroupPermission userGroupId="ADMIN" userPermissionId="TRANSFERS_DISCREPANCY_VIEW" fromDate="0"/>
    <moqui.security.UserGroupPermission userGroupId="ADMIN" userPermissionId="TRANSFERS_BULK_CREATE" fromDate="0"/>
    <moqui.security.UserGroupPermission userGroupId="ADMIN" userPermissionId="BOPIS_REQUEST_TRANSFER_UPDATE" fromDate="0"/>
    <moqui.security.UserGroupPermission userGroupId="ADMIN" userPermissionId="BOPIS_POD_UPDATE" fromDate="0"/>
    <moqui.security.UserGroupPermission userGroupId="ADMIN" userPermissionId="FULFILLMENT_VIEW_ALL_PICKERS" fromDate="0"/>
    <moqui.security.UserGroupPermission userGroupId="ADMIN" userPermissionId="INV_COUNT_VAR_LOG" fromDate="0"/>
    <moqui.security.UserGroupPermission userGroupId="ADMIN" userPermissionId="ROUTING_TEST_DRIVE_VIEW" fromDate="0"/>
    <moqui.security.UserGroupPermission userGroupId="ADMIN" userPermissionId="SECURITY_ADMIN" fromDate="0"/>
    <moqui.security.UserGroupPermission userGroupId="ADMIN" userPermissionId="SECURITY_VIEW" fromDate="0"/>
    <moqui.security.UserGroupPermission userGroupId="ADMIN" userPermissionId="PIM_PRODUCT_CREATE" fromDate="0"/>
    <moqui.security.UserGroupPermission userGroupId="ADMIN" userPermissionId="PIM_FEATURE_CREATE" fromDate="0"/>
    <moqui.security.UserGroupPermission userGroupId="ADMIN" userPermissionId="ORD_TRANSFER_ORDER_VIEW" fromDate="0"/>
    <moqui.security.UserGroupPermission userGroupId="ADMIN" userPermissionId="FF_ORDER_LOOKUP_VIEW" fromDate="0"/>
    <moqui.security.UserGroupPermission userGroupId="ADMIN" userPermissionId="FF_INVOICING_STATUS_VIEW" fromDate="0"/>
    <moqui.security.UserGroupPermission userGroupId="ADMIN" userPermissionId="PARTYMGR_UPDATE" fromDate="0"/>
    <moqui.security.UserGroupPermission userGroupId="ADMIN" userPermissionId="PARTYMGR_VIEW" fromDate="0"/>
    <moqui.security.UserGroupPermission userGroupId="ADMIN" userPermissionId="PARTYMGR_PCM_CREATE" fromDate="0"/>
    <moqui.security.UserGroupPermission userGroupId="ADMIN" userPermissionId="PARTYMGR_PCM_UPDATE" fromDate="0"/>
    <moqui.security.UserGroupPermission userGroupId="ADMIN" userPermissionId="PARTYMGR_PCM_DELETE" fromDate="0"/>
    <moqui.security.UserGroupPermission userGroupId="ADMIN" userPermissionId="PIM_PRODUCT_VIEW" fromDate="0"/>
    <moqui.security.UserGroupPermission userGroupId="ADMIN" userPermissionId="ORDERMGR_VIEW" fromDate="0"/>
    <moqui.security.UserGroupPermission userGroupId="ADMIN" userPermissionId="ORDERMGR_CREATE" fromDate="0"/>
    <moqui.security.UserGroupPermission userGroupId="ADMIN" userPermissionId="ORDERMGR_UPDATE" fromDate="0"/>
    <moqui.security.UserGroupPermission userGroupId="ADMIN" userPermissionId="ORD_SALES_ORDER_VIEW" fromDate="0"/>
    <moqui.security.UserGroupPermission userGroupId="ADMIN" userPermissionId="ORD_SALES_ORDER_CREATE" fromDate="0"/>
    <moqui.security.UserGroupPermission userGroupId="ADMIN" userPermissionId="RELATNSHIP_CUSTOMER_VIEW" fromDate="0"/>
    <moqui.security.UserGroupPermission userGroupId="ADMIN" userPermissionId="RELATNSHIP_CUSTOMER_CREATE" fromDate="0"/>

    <!-- CSR -->
    <moqui.security.UserGroupPermission userGroupId="CSR" userPermissionId="COMMERCEUSER_VIEW" fromDate="0"/>
    <moqui.security.UserGroupPermission userGroupId="CSR" userPermissionId="ORD_SALES_ORDER_CNCL" fromDate="0"/>
    <moqui.security.UserGroupPermission userGroupId="CSR" userPermissionId="PARTYMGR_PCM_CREATE" fromDate="0"/>
    <moqui.security.UserGroupPermission userGroupId="CSR" userPermissionId="PARTYMGR_PCM_UPDATE" fromDate="0"/>
    <moqui.security.UserGroupPermission userGroupId="CSR" userPermissionId="PARTYMGR_PCM_DELETE" fromDate="0"/>
    <moqui.security.UserGroupPermission userGroupId="CSR" userPermissionId="PARTYMGR_STS_UPDATE" fromDate="0"/>
    <moqui.security.UserGroupPermission userGroupId="CSR" userPermissionId="PARTYMGR_UPDATE" fromDate="0"/>
    <moqui.security.UserGroupPermission userGroupId="CSR" userPermissionId="PARTYMGR_VIEW" fromDate="0"/>
    <moqui.security.UserGroupPermission userGroupId="CSR" userPermissionId="PIM_PRODUCT_VIEW" fromDate="0"/>
    <moqui.security.UserGroupPermission userGroupId="CSR" userPermissionId="ORDERMGR_CREATE" fromDate="0"/>
    <moqui.security.UserGroupPermission userGroupId="CSR" userPermissionId="ORDERMGR_UPDATE" fromDate="0"/>
    <moqui.security.UserGroupPermission userGroupId="CSR" userPermissionId="ORDERMGR_VIEW" fromDate="0"/>
    <moqui.security.UserGroupPermission userGroupId="CSR" userPermissionId="ORD_CRT_EVENT_VIEW" fromDate="0"/>
    <moqui.security.UserGroupPermission userGroupId="CSR" userPermissionId="ORD_SALES_ORDER_ADMIN" fromDate="0"/>
    <moqui.security.UserGroupPermission userGroupId="CSR" userPermissionId="ORD_SALES_ORDER_CREATE" fromDate="0"/>
    <moqui.security.UserGroupPermission userGroupId="CSR" userPermissionId="ORD_SALES_ORDER_VIEW" fromDate="0"/>
    <moqui.security.UserGroupPermission userGroupId="CSR" userPermissionId="RELATNSHIP_CUSTOMER_CREATE" fromDate="0"/>
    <moqui.security.UserGroupPermission userGroupId="CSR" userPermissionId="RELATNSHIP_CUSTOMER_VIEW" fromDate="0"/>

    <!-- ORDER_MANAGER -->
    <moqui.security.UserGroupPermission userGroupId="ORDER_MANAGER" userPermissionId="COMMERCEUSER_VIEW" fromDate="0"/>
    <moqui.security.UserGroupPermission userGroupId="ORDER_MANAGER" userPermissionId="ORD_SALES_ORDER_CNCL" fromDate="0"/>
    <moqui.security.UserGroupPermission userGroupId="ORDER_MANAGER" userPermissionId="PARTYMGR_PCM_CREATE" fromDate="0"/>
    <moqui.security.UserGroupPermission userGroupId="ORDER_MANAGER" userPermissionId="PARTYMGR_PCM_UPDATE" fromDate="0"/>
    <moqui.security.UserGroupPermission userGroupId="ORDER_MANAGER" userPermissionId="PARTYMGR_PCM_DELETE" fromDate="0"/>
    <moqui.security.UserGroupPermission userGroupId="ORDER_MANAGER" userPermissionId="PARTYMGR_STS_UPDATE" fromDate="0"/>
    <moqui.security.UserGroupPermission userGroupId="ORDER_MANAGER" userPermissionId="PARTYMGR_UPDATE" fromDate="0"/>
    <moqui.security.UserGroupPermission userGroupId="ORDER_MANAGER" userPermissionId="PARTYMGR_VIEW" fromDate="0"/>
    <moqui.security.UserGroupPermission userGroupId="ORDER_MANAGER" userPermissionId="PIM_PRODUCT_VIEW" fromDate="0"/>
    <moqui.security.UserGroupPermission userGroupId="ORDER_MANAGER" userPermissionId="SECURITY_CREATE" fromDate="0"/>
    <moqui.security.UserGroupPermission userGroupId="ORDER_MANAGER" userPermissionId="ORDERMGR_CREATE" fromDate="0"/>
    <moqui.security.UserGroupPermission userGroupId="ORDER_MANAGER" userPermissionId="ORDERMGR_UPDATE" fromDate="0"/>
    <moqui.security.UserGroupPermission userGroupId="ORDER_MANAGER" userPermissionId="ORDERMGR_VIEW" fromDate="0"/>
    <moqui.security.UserGroupPermission userGroupId="ORDER_MANAGER" userPermissionId="ORD_CRT_EVENT_VIEW" fromDate="0"/>
    <moqui.security.UserGroupPermission userGroupId="ORDER_MANAGER" userPermissionId="ORD_SALES_ORDER_ADMIN" fromDate="0"/>
    <moqui.security.UserGroupPermission userGroupId="ORDER_MANAGER" userPermissionId="ORD_SALES_ORDER_CREATE" fromDate="0"/>
    <moqui.security.UserGroupPermission userGroupId="ORDER_MANAGER" userPermissionId="ORD_SALES_ORDER_EDIT" fromDate="0"/>
    <moqui.security.UserGroupPermission userGroupId="ORDER_MANAGER" userPermissionId="ORD_SALES_ORDER_VIEW" fromDate="0"/>
    <moqui.security.UserGroupPermission userGroupId="ORDER_MANAGER" userPermissionId="RELATNSHIP_CUSTOMER_CREATE" fromDate="0"/>
    <moqui.security.UserGroupPermission userGroupId="ORDER_MANAGER" userPermissionId="RELATNSHIP_CUSTOMER_VIEW" fromDate="0"/>
    <moqui.security.UserGroupPermission userGroupId="ORDER_MANAGER" userPermissionId="MOVE_SO_ITEM" fromDate="0"/>

    <!-- WAREHOUSE_MANAGER -->
    <moqui.security.UserGroupPermission userGroupId="WAREHOUSE_MANAGER" userPermissionId="COMMERCEUSER_VIEW" fromDate="0"/>
    <moqui.security.UserGroupPermission userGroupId="WAREHOUSE_MANAGER" userPermissionId="ORD_SALES_ORDER_CNCL" fromDate="0"/>
    <moqui.security.UserGroupPermission userGroupId="WAREHOUSE_MANAGER" userPermissionId="PARTYMGR_PCM_CREATE" fromDate="0"/>
    <moqui.security.UserGroupPermission userGroupId="WAREHOUSE_MANAGER" userPermissionId="PARTYMGR_PCM_UPDATE" fromDate="0"/>
    <moqui.security.UserGroupPermission userGroupId="WAREHOUSE_MANAGER" userPermissionId="INV_COUNT_ADMIN" fromDate="0"/>
    <moqui.security.UserGroupPermission userGroupId="WAREHOUSE_MANAGER" userPermissionId="INV_COUNT_LOCK_RLS" fromDate="0"/>
    <moqui.security.UserGroupPermission userGroupId="WAREHOUSE_MANAGER" userPermissionId="INV_CNT_VIEW_QOH" fromDate="0"/>
    <moqui.security.UserGroupPermission userGroupId="WAREHOUSE_MANAGER" userPermissionId="INV_COUNT_SUBMIT" fromDate="0"/>
    <moqui.security.UserGroupPermission userGroupId="WAREHOUSE_MANAGER" userPermissionId="INV_COUNT_PRE_START" fromDate="0"/>
    <moqui.security.UserGroupPermission userGroupId="WAREHOUSE_MANAGER" userPermissionId="PREVIEW_COUNT_ITEM" fromDate="0"/>
    <moqui.security.UserGroupPermission userGroupId="WAREHOUSE_MANAGER" userPermissionId="RECEIVING_ADMIN" fromDate="0"/>
    <moqui.security.UserGroupPermission userGroupId="WAREHOUSE_MANAGER" userPermissionId="ORDERMGR_CREATE" fromDate="0"/>
    <moqui.security.UserGroupPermission userGroupId="WAREHOUSE_MANAGER" userPermissionId="ORDERMGR_UPDATE" fromDate="0"/>

    <!-- MERCHANDISE_MGR -->
    <moqui.security.UserGroupPermission userGroupId="MERCHANDISE_MGR" userPermissionId="COMMERCEUSER_VIEW" fromDate="0"/>
    <moqui.security.UserGroupPermission userGroupId="MERCHANDISE_MGR" userPermissionId="ORD_SALES_ORDER_CNCL" fromDate="0"/>
    <moqui.security.UserGroupPermission userGroupId="MERCHANDISE_MGR" userPermissionId="PIM_PRODUCT_VIEW" fromDate="0"/>
    <moqui.security.UserGroupPermission userGroupId="MERCHANDISE_MGR" userPermissionId="ORDERMGR_UPDATE" fromDate="0"/>
    <moqui.security.UserGroupPermission userGroupId="MERCHANDISE_MGR" userPermissionId="ORDERMGR_VIEW" fromDate="0"/>
    <moqui.security.UserGroupPermission userGroupId="MERCHANDISE_MGR" userPermissionId="ORD_SALES_ORDER_ADMIN" fromDate="0"/>
    <moqui.security.UserGroupPermission userGroupId="MERCHANDISE_MGR" userPermissionId="ORD_SALES_ORDER_VIEW" fromDate="0"/>

    <!-- STORE_MANAGER -->
    <moqui.security.UserGroupPermission userGroupId="STORE_MANAGER" userPermissionId="BOPIS_APP_VIEW" fromDate="0"/>
    <moqui.security.UserGroupPermission userGroupId="STORE_MANAGER" userPermissionId="FULFILLMENT_APP_VIEW" fromDate="0"/>
    <moqui.security.UserGroupPermission userGroupId="STORE_MANAGER" userPermissionId="INVCOUNT_APP_VIEW" fromDate="0"/>
    <moqui.security.UserGroupPermission userGroupId="STORE_MANAGER" userPermissionId="RECEIVING_APP_VIEW" fromDate="0"/>
    <moqui.security.UserGroupPermission userGroupId="STORE_MANAGER" userPermissionId="COMMERCEUSER_VIEW" fromDate="0"/>
    <moqui.security.UserGroupPermission userGroupId="STORE_MANAGER" userPermissionId="PARTYMGR_PCM_CREATE" fromDate="0"/>
    <moqui.security.UserGroupPermission userGroupId="STORE_MANAGER" userPermissionId="PARTYMGR_PCM_UPDATE" fromDate="0"/>
    <moqui.security.UserGroupPermission userGroupId="STORE_MANAGER" userPermissionId="INV_COUNT_ADMIN" fromDate="0"/>
    <moqui.security.UserGroupPermission userGroupId="STORE_MANAGER" userPermissionId="INV_COUNT_LOCK_RLS" fromDate="0"/>
    <moqui.security.UserGroupPermission userGroupId="STORE_MANAGER" userPermissionId="INV_CNT_VIEW_QOH" fromDate="0"/>
    <moqui.security.UserGroupPermission userGroupId="STORE_MANAGER" userPermissionId="INV_COUNT_SUBMIT" fromDate="0"/>
    <moqui.security.UserGroupPermission userGroupId="STORE_MANAGER" userPermissionId="INV_COUNT_PRE_START" fromDate="0"/>
    <moqui.security.UserGroupPermission userGroupId="STORE_MANAGER" userPermissionId="PREVIEW_COUNT_ITEM" fromDate="0"/>
    <moqui.security.UserGroupPermission userGroupId="STORE_MANAGER" userPermissionId="RECEIVING_ADMIN" fromDate="0"/>
    <moqui.security.UserGroupPermission userGroupId="STORE_MANAGER" userPermissionId="ORDERMGR_CREATE" fromDate="0"/>
    <moqui.security.UserGroupPermission userGroupId="STORE_MANAGER" userPermissionId="ORDERMGR_UPDATE" fromDate="0"/>
    <moqui.security.UserGroupPermission userGroupId="STORE_MANAGER" userPermissionId="SF_UNLOCK_ORDER" fromDate="0"/>

    <moqui.basic.Enumeration enumId="MaargSecGrp" description="Maarg Security group mapping"/>
    <co.hotwax.integration.IntegrationTypeMapping
            integrationMappingId="SEC_GRP_ADMIN_ADV"
            integrationTypeId="MaargSecGrp"
            mappingKey="ADMIN_ADV"
            mappingValue="SUPER"
            description="Map OFBiz SUPER security group to internal ADMIN_ADV user group"/>

    <co.hotwax.integration.IntegrationTypeMapping
            integrationMappingId="SEC_GRP_ADMIN"
            integrationTypeId="MaargSecGrp"
            mappingKey="ADMIN"
            mappingValue="COMMERCE_SUPER"
            description="Map OFBiz COMMERCE_SUPER security group to internal ADMIN user group"/>

    <co.hotwax.integration.IntegrationTypeMapping
            integrationMappingId="SEC_GRP_CSR"
            integrationTypeId="MaargSecGrp"
            mappingKey="CSR"
            mappingValue="CSR"
            description="Map OFBiz CSR security group to Customer Service Representatives user group"/>

    <co.hotwax.integration.IntegrationTypeMapping
            integrationMappingId="SEC_GRP_STORE_MGR"
            integrationTypeId="MaargSecGrp"
            mappingKey="STORE_MANAGER"
            mappingValue="STORE_MANAGER"
            description="Map OFBiz Store Manager security group to internal STORE_MANAGER user group"/>

    <co.hotwax.integration.IntegrationTypeMapping
            integrationMappingId="SEC_GRP_ORDER_MGR"
            integrationTypeId="MaargSecGrp"
            mappingKey="ORDER_MANAGER"
            mappingValue="ORDER_MANAGER"
            description="Map OFBiz Order Manager security group to internal ORDER_MANAGER user group"/>

    <co.hotwax.integration.IntegrationTypeMapping
            integrationMappingId="SEC_GRP_WH_MGR"
            integrationTypeId="MaargSecGrp"
            mappingKey="WAREHOUSE_MANAGER"
            mappingValue="WAREHOUSE_MANAGER"
            description="Map OFBiz Warehouse Manager security group to internal WAREHOUSE_MANAGER user group"/>

    <co.hotwax.integration.IntegrationTypeMapping
            integrationMappingId="SEC_GRP_MER_MGR"
            integrationTypeId="MaargSecGrp"
            mappingKey="MERCHANDISE_MGR"
            mappingValue="MERCHANDISE_MGR"
            description="Map OFBiz Merchandise Manager security group to internal MERCHANDISE_MGR user group"/>

    <!-- Add PRODUCTS_APP_VIEW permission for Products app -->
    <org.apache.ofbiz.security.securitygroup.SecurityPermission permissionId="PRODUCTS_APP_VIEW" description="View Products App"/>
    <org.apache.ofbiz.security.securitygroup.SecurityGroupPermission groupId="COMMERCE_SUPER" permissionId="PRODUCTS_APP_VIEW" fromDate="2000-01-01 00:00:00.000"/>
    <org.apache.ofbiz.security.securitygroup.SecurityGroupPermission groupId="SUPER" permissionId="PRODUCTS_APP_VIEW" fromDate="2000-01-01 00:00:00.000"/>
    <org.apache.ofbiz.security.securitygroup.SecurityGroupPermission groupId="SGC_ADMIN" permissionId="PRODUCTS_APP_VIEW" fromDate="2000-01-01 00:00:00.000"/>
    <org.apache.ofbiz.security.securitygroup.SecurityGroupPermission groupId="SGC_PROD" permissionId="PRODUCTS_APP_VIEW" fromDate="2000-01-01 00:00:00.000"/>
    <org.apache.ofbiz.security.securitygroup.SecurityGroupPermission groupId="MERCHANDISE_MGR" permissionId="PRODUCTS_APP_VIEW" fromDate="2000-01-01 00:00:00.000"/>

    <!-- Add Products app action permissions -->
    <org.apache.ofbiz.security.securitygroup.SecurityPermission permissionId="PIM_PRODUCT_VIEW" description="View Products"/>
    <org.apache.ofbiz.security.securitygroup.SecurityPermission permissionId="PIM_PRODUCT_CREATE" description="Create Products"/>
    <org.apache.ofbiz.security.securitygroup.SecurityPermission permissionId="PIM_PRODUCT_ADMIN" description="Product Admin Permission"/>
    <org.apache.ofbiz.security.securitygroup.SecurityPermission permissionId="PIM_FEATURE_CREATE" description="Create Product Features"/>
    <org.apache.ofbiz.security.securitygroup.SecurityPermission permissionId="PIM_FEATURE_ADMIN" description="Features Admin Permission"/>
    <org.apache.ofbiz.security.securitygroup.SecurityGroupPermission groupId="COMMERCE_SUPER" permissionId="PIM_PRODUCT_ADMIN" fromDate="2000-01-01 00:00:00.000"/>
    <org.apache.ofbiz.security.securitygroup.SecurityGroupPermission groupId="COMMERCE_SUPER" permissionId="PIM_FEATURE_ADMIN" fromDate="2000-01-01 00:00:00.000"/>
    <org.apache.ofbiz.security.securitygroup.SecurityGroupPermission groupId="SUPER" permissionId="PIM_PRODUCT_ADMIN" fromDate="2000-01-01 00:00:00.000"/>
    <org.apache.ofbiz.security.securitygroup.SecurityGroupPermission groupId="SUPER" permissionId="PIM_FEATURE_ADMIN" fromDate="2000-01-01 00:00:00.000"/>
    <org.apache.ofbiz.security.securitygroup.SecurityGroupPermission groupId="SGC_ADMIN" permissionId="PIM_PRODUCT_ADMIN" fromDate="2000-01-01 00:00:00.000"/>
    <org.apache.ofbiz.security.securitygroup.SecurityGroupPermission groupId="SGC_ADMIN" permissionId="PIM_FEATURE_ADMIN" fromDate="2000-01-01 00:00:00.000"/>
    <org.apache.ofbiz.security.securitygroup.SecurityGroupPermission groupId="SGC_PROD" permissionId="PIM_PRODUCT_VIEW" fromDate="2000-01-01 00:00:00.000"/>
    <org.apache.ofbiz.security.securitygroup.SecurityGroupPermission groupId="SGC_PROD" permissionId="PIM_PRODUCT_CREATE" fromDate="2000-01-01 00:00:00.000"/>
    <org.apache.ofbiz.security.securitygroup.SecurityGroupPermission groupId="SGC_PROD" permissionId="PIM_PRODUCT_ADMIN" fromDate="2000-01-01 00:00:00.000"/>
    <org.apache.ofbiz.security.securitygroup.SecurityGroupPermission groupId="SGC_PROD" permissionId="PIM_FEATURE_CREATE" fromDate="2000-01-01 00:00:00.000"/>
    <org.apache.ofbiz.security.securitygroup.SecurityGroupPermission groupId="SGC_PROD" permissionId="PIM_FEATURE_ADMIN" fromDate="2000-01-01 00:00:00.000"/>
    <org.apache.ofbiz.security.securitygroup.SecurityGroupPermission groupId="MERCHANDISE_MGR" permissionId="PIM_PRODUCT_VIEW" fromDate="2000-01-01 00:00:00.000"/>
    <!-- Add ORDERMGR_APP_VIEW permission for Order Manager app -->
    <org.apache.ofbiz.security.securitygroup.SecurityPermission permissionId="ORDERMGR_APP_VIEW" description="View Order Manager App"/>
    <org.apache.ofbiz.security.securitygroup.SecurityGroupPermission groupId="COMMERCE_SUPER" permissionId="ORDERMGR_APP_VIEW" fromDate="2000-01-01 00:00:00.000"/>

    <!-- Default ship SLA for the brokering queue: unbrokered ship groups get estimatedShipDate = orderDate + 1 day (partial record — sets only defaultDaysToShip on the existing _NA_ facility) -->
    <org.apache.ofbiz.product.facility.Facility facilityId="_NA_" defaultDaysToShip="1"/>
    <co.hotwax.datamanager.DataManagerConfig configId="IMPORT_PO" importServiceName="co.hotwax.orderledger.order.PurchaseOrderServices.store#PurchaseOrder" description="Purchase Order" fileNamePattern="Purchase_Order_${sequence}"/>

    <!-- hotwax.user login was previously gated behind type="demo" data (JA_Demo_AJ_HCUserData.xml),
         so existing instances have the HOTWAX_USER Party (seeded by ofbiz-oms-udm's ext data,
         a hard dependency of oms) but never had a way to log in as it. Add the account so
         existing instances get the same bootstrap login new installs now get. -->
    <moqui.security.UserAccount userId="HOTWAX_USER" username="hotwax.user" userFullName="Hotwax User"
                                currentPassword="6c393d0e69cbbb603f71c0672a25dcf5b195897ef94372818e3358e56047bd44" passwordHashType="SHA-256" passwordBase64="N"
                                currencyUomId="USD" locale="en_US" timeZone=""
                                emailAddress="support@hotwax.co" requirePasswordChange="Y"/>
    <moqui.security.UserGroupMember userGroupId="ADMIN" userId="HOTWAX_USER" fromDate="1265184000000"/>
    <moqui.security.UserGroupMember userGroupId="ADMIN_ADV" userId="HOTWAX_USER" fromDate="1265184000000"/>
</entity-facade-xml>
```

### oms
**Release tag:** v3.0.0-RC1    **Exact file:** upgrade/v3.0.0-RC1/UpgradeSql.sql    **Type:** SQL

```sql
ALTER TABLE ORDER_ITEM_SHIP_GROUP ADD EXTERNAL_ID VARCHAR(255);
CREATE INDEX IDX_ORD_SHPGRP_EXTID ON ORDER_ITEM_SHIP_GROUP (EXTERNAL_ID);

-- Funnel dashboard queries now use ORDER_HEADER.ENTRY_DATE instead of ORDER_ITEM_SHIP_GROUP.CREATED_STAMP
DROP INDEX IDX_ORD_SHPGRP_CRT_STMP ON ORDER_ITEM_SHIP_GROUP;

-- Normalize legacy high-risk tasks to the canonical OMS blocking-hold type/purpose pair.
UPDATE WORK_EFFORT
SET WORK_EFFORT_TYPE_ID = 'RESOLVE_ONHOLD_ORDER',
    WORK_EFFORT_PURPOSE_TYPE_ID = 'REVIEW_RISK_ORDER'
WHERE WORK_EFFORT_TYPE_ID = 'REVIEW_RISK_ORDER';

-- Rename only the legacy bad-address purpose used by the canonical Poorti/OMS task model.
-- ORDER_HOLD rows belong to the separate connector lifecycle and are intentionally unchanged.
UPDATE WORK_EFFORT
SET WORK_EFFORT_PURPOSE_TYPE_ID = 'INVALID_ADDRESS'
WHERE WORK_EFFORT_TYPE_ID = 'RESOLVE_ONHOLD_ORDER'
  AND WORK_EFFORT_PURPOSE_TYPE_ID = 'ORD_HOLD_BAD_ADDR';
```

### oms
**Release tag:** v3.1.0    **Exact file:** upgrade/v3.1.0/UpgradeData.xml    **Type:** XML

```xml
<?xml version="1.0" encoding="UTF-8"?>
<entity-facade-xml type="ext-upgrade">
    <!-- Seed security groups referenced by existing Products app permission grants. -->
    <org.apache.ofbiz.security.securitygroup.SecurityGroup groupId="SUPER" groupName="Super"
        description="Super admin group, has all *_ADMIN permission loaded as seed data"/>
    <org.apache.ofbiz.security.securitygroup.SecurityGroup groupId="SGC_ADMIN" groupName="Admin"
        description="Group for admin-related permissions." groupTypeEnumId="PRM_CLASS_TYPE"/>
    <org.apache.ofbiz.security.securitygroup.SecurityGroup groupId="SGC_PROD" groupName="Products"
        description="Group for product-related permissions." groupTypeEnumId="PRM_CLASS_TYPE"/>
    <org.apache.ofbiz.security.securitygroup.SecurityGroup groupId="MERCHANDISE_MGR" groupName="Merchandising Manager"
        description="Merchandising Manager"/>

    <moqui.security.UserPermission userPermissionId="VIEW_DB_DATASOURCE" description="View datasource connection details on About page"/>
    <moqui.security.UserGroupPermission userGroupId="ADMIN" userPermissionId="VIEW_DB_DATASOURCE"/>

    <moqui.basic.StatusFlowTransition statusFlowId="TO_Receive_Only" statusId="ITEM_PENDING_RECEIPT" toStatusId="ITEM_PENDING_RECEIPT" transitionSequence="2" transitionName="Partial Receive Validation" conditionExpression="directStatusChange == false"/>
    <moqui.basic.StatusFlowTransition statusFlowId="TO_Fulfill_And_Receive" statusId="ITEM_PENDING_FULFILL" toStatusId="ITEM_PENDING_FULFILL" transitionSequence="3" transitionName="Partial Fulfill Validation" conditionExpression="directStatusChange == false"/>
    <moqui.basic.StatusFlowTransition statusFlowId="TO_Fulfill_And_Receive" statusId="ITEM_PENDING_RECEIPT" toStatusId="ITEM_PENDING_RECEIPT" transitionSequence="4" transitionName="Partial Receive Validation" conditionExpression="false"/>

    <!-- OMS_API authorizations for the application user groups, moved here from
         component://oms/data/DH_ExtSeed_UserPermissionData.xml so they live with the artifact group. -->
    <artifactGroups artifactGroupId="OMS_API" description="Commerce OMS API (via root resource)">
        <artifacts artifactName="component://oms/screen/Oms.xml" artifactTypeEnumId="AT_XML_SCREEN" inheritAuthz="Y"/>
        <artifacts artifactTypeEnumId="AT_REST_PATH" inheritAuthz="Y" artifactName="/oms"/>
        <!-- Full permissions for the ADMIN user group -->
        <authz artifactAuthzId="OMS_API_ADMIN" userGroupId="ADMIN" authzTypeEnumId="AUTHZT_ALWAYS" authzActionEnumId="AUTHZA_ALL"/>
        <!-- Full permissions for the application user groups -->
        <authz artifactAuthzId="OMS_API_SM" userGroupId="STORE_MANAGER" authzTypeEnumId="AUTHZT_ALWAYS" authzActionEnumId="AUTHZA_ALL"/>
        <authz artifactAuthzId="OMS_API_WM" userGroupId="WAREHOUSE_MANAGER" authzTypeEnumId="AUTHZT_ALWAYS" authzActionEnumId="AUTHZA_ALL"/>
        <authz artifactAuthzId="OMS_API_CSR" userGroupId="CSR" authzTypeEnumId="AUTHZT_ALWAYS" authzActionEnumId="AUTHZA_ALL"/>
        <authz artifactAuthzId="OMS_API_OM" userGroupId="ORDER_MANAGER" authzTypeEnumId="AUTHZT_ALWAYS" authzActionEnumId="AUTHZA_ALL"/>
        <authz artifactAuthzId="OMS_API_MM" userGroupId="MERCHANDISE_MGR" authzTypeEnumId="AUTHZT_ALWAYS" authzActionEnumId="AUTHZA_ALL"/>
    </artifactGroups>
    <co.hotwax.datamanager.DataManagerConfig configId="IMP_ATP_PROD_FAC" importServiceName="co.hotwax.atp.AtpServices.import#AtpProductFacility" description="Import ATP Product Facility (Moqui Native)" scriptTitle="Import ATP product facility" multiThreading="N"/>
    <moqui.security.UserPermission userPermissionId="INV_COUNT_CREATE" description="User can create custom count without need to upload csv"/>
    <moqui.security.UserGroupPermission userGroupId="ADMIN" userPermissionId="INV_COUNT_CREATE" fromDate="0"/>
    <moqui.security.UserGroupPermission userGroupId="WAREHOUSE_MANAGER" userPermissionId="INV_COUNT_CREATE" fromDate="0"/>
    <moqui.security.UserGroupPermission userGroupId="STORE_MANAGER" userPermissionId="INV_COUNT_CREATE" fromDate="0"/>

    <moqui.security.UserPermission userPermissionId="JOB_MANAGER_ACCXUI_APP_VIEW" description="View Job Manager Accxui App"/>
    <moqui.security.UserPermission userPermissionId="RECEIVING_LEGACY_APP_VIEW" description="View Receiving Legacy App"/>
    <moqui.security.UserGroupPermission userGroupId="ADMIN" userPermissionId="JOB_MANAGER_ACCXUI_APP_VIEW" fromDate="0"/>
    <moqui.security.UserPermission userPermissionId="ORDERMGR_APP_VIEW" description="View Order Manager App"/>
    <moqui.security.UserGroupPermission userGroupId="ADMIN" userPermissionId="ORDERMGR_APP_VIEW" fromDate="0"/>

    <!-- Renamed IMPO_PRD_CODE to MDM_IMP_PROD_IDENT and fixed importServiceName so connector
         components (e.g. mantle-netsuite-connector) can expand this same generic MDM config.
         Mirrors the row updated in ED_Ext_ExtCommerceData.xml (loaded on fresh installs). -->
    <co.hotwax.datamanager.DataManagerConfig configId="MDM_IMP_PROD_IDENT" importServiceName="co.hotwax.oms.product.ProductServices.store#ProductIdentification" description="Create and Update Product ERP Code" scriptTitle="Create and Update Product ERP Code" importPath="/home/{SFTP-USER}/{FOLDER}"/>

    <!-- Added MDM_IMP_FACILITY DataManagerConfig for facility data setup service path.
         Mirrors the row added in ED_Ext_ExtCommerceData.xml (loaded on fresh installs). -->
    <co.hotwax.datamanager.DataManagerConfig configId="MDM_IMP_FACILITY" importServiceName="co.hotwax.oms.facility.FacilityServices.store#Facility" description="Import Facility" scriptTitle="Facility data" fileNamePattern="Facility_${sequence}"/>
    <moqui.basic.Enumeration enumId="INV_RES_CREATE" enumTypeId="IID_REASON" enumCode="INV_RESERVATION_CREATE" description="Inventory reservation created" enumName="Inventory reservation created"/>
    <moqui.basic.Enumeration enumId="INV_RES_RELEASE" enumTypeId="IID_REASON" enumCode="INV_RESERVATION_RELEASE" description="Inventory reservation released" enumName="Inventory reservation released"/>
</entity-facade-xml>
```

### oms
**Release tag:** v3.1.0    **Exact file:** upgrade/v3.1.0/UpgradeSql.sql    **Type:** SQL

```sql
ALTER TABLE ORDER_HEADER
    ADD COLUMN RISK_RECOMMENDATION_ENUM_ID VARCHAR(40) NULL,
    ADD COLUMN RISK_LEVEL_ENUM_ID VARCHAR(40) NULL;


ALTER TABLE RULE_GROUP
    ADD CONSTRAINT RG_PROD_STR
        FOREIGN KEY (PRODUCT_STORE_ID)
            REFERENCES PRODUCT_STORE (PRODUCT_STORE_ID);

-- ShopifyProdLocActivation
ALTER TABLE SHOPIFY_PROD_LOC_ACTIVATION
    ADD COLUMN ACTIVATED_AT DATETIME(3);

DROP INDEX IDX_PROD_LOC_ACT
    ON SHOPIFY_PROD_LOC_ACTIVATION;

ALTER TABLE SHOPIFY_PROD_LOC_ACTIVATION
DROP COLUMN ACTIVATED;

CREATE INDEX IDX_SHOP_PRODUCT_ID
    ON SHOPIFY_SHOP_PRODUCT (SHOP_ID, PRODUCT_ID);

/* Add the PRDS_SM_PRDSTR foreign key on PRODUCT_STORE_SHIPMENT_METH.

 ProductStoreShipmentMeth is a join entity between ProductStore and
 ShipmentMethodType. Both sides are required, so both should carry a
 foreign key. The ShipmentMethodType side already has one. The
 ProductStore side was lost when the model was converted from OFBiz,
 so PRODUCT_STORE_ID carried no constraint.

 The relationship is now type="one" in the entity model. Moqui creates
 foreign keys only when it creates the table, so a database that already
 has PRODUCT_STORE_SHIPMENT_METH needs this statement run by hand.

 Before running, check for rows that would violate the constraint:

   SELECT COUNT(*) FROM PRODUCT_STORE_SHIPMENT_METH m
    WHERE m.PRODUCT_STORE_ID IS NOT NULL
      AND NOT EXISTS (SELECT 1 FROM PRODUCT_STORE s
                       WHERE s.PRODUCT_STORE_ID = m.PRODUCT_STORE_ID);

 The count must be 0. Delete or repair any orphan rows first.
 NULL PRODUCT_STORE_ID is allowed by the constraint and does not block it.*/

ALTER TABLE PRODUCT_STORE_SHIPMENT_METH
    ADD CONSTRAINT PRDS_SM_PRDSTR FOREIGN KEY (PRODUCT_STORE_ID) REFERENCES PRODUCT_STORE (PRODUCT_STORE_ID);
-- Migrate legacy ATP safety stock and threshold rule actions to 'minimum-stock'
UPDATE RULE_ACTION SET FIELD_NAME = 'minimum-stock'
    WHERE ACTION_TYPE_ENUM_ID IN ('ATP_SAFETY_STOCK', 'ATP_THRESHOLD')
        AND FIELD_NAME != 'minimum-stock';
```

### oms
**Release tag:** v3.1.1    **Exact file:** upgrade/v3.1.1/UpgradeData.xml    **Type:** XML

```xml
<?xml version="1.0" encoding="UTF-8"?>
<entity-facade-xml type="ext-upgrade">
</entity-facade-xml>
```

### oms
**Release tag:** v3.1.2    **Exact file:** upgrade/v3.1.2/UpgradeData.xml    **Type:** XML

```xml
<?xml version="1.0" encoding="UTF-8"?>
<entity-facade-xml type="ext-upgrade">
</entity-facade-xml>
```

### oms
**Release tag:** v3.1.3    **Exact file:** upgrade/v3.1.3/UpgradeData.xml    **Type:** XML

```xml
<?xml version="1.0" encoding="UTF-8"?>
<entity-facade-xml type="ext-upgrade">
    <moqui.basic.StatusFlowTransition statusFlowId="Default" statusId="TASK_CREATED" toStatusId="TASK_COMPLETED" transitionName="Complete"/>
    <moqui.basic.StatusFlowTransition statusFlowId="Default" statusId="TASK_ON_HOLD" toStatusId="TASK_COMPLETED" transitionName="Complete"/>
</entity-facade-xml>
```

### oms
**Release tag:** v3.1.4    **Exact file:** upgrade/v3.1.4/UpgradeData.xml    **Type:** XML

```xml
<?xml version="1.0" encoding="UTF-8"?>
<entity-facade-xml type="ext-upgrade">
</entity-facade-xml>
```

### oms
**Release tag:** v3.1.5    **Exact file:** upgrade/v3.1.5/UpgradeData.xml    **Type:** XML

```xml
<?xml version="1.0" encoding="UTF-8"?>
<entity-facade-xml type="ext-upgrade">
</entity-facade-xml>
```

### oms
**Release tag:** v3.1.6    **Exact file:** upgrade/v3.1.6/UpgradeData.xml    **Type:** XML

```xml
<?xml version="1.0" encoding="UTF-8"?>
<entity-facade-xml type="ext-upgrade">
</entity-facade-xml>
```

### oms
**Release tag:** v3.1.7    **Exact file:** upgrade/v3.1.7/UpgradeData.xml    **Type:** XML

```xml
<?xml version="1.0" encoding="UTF-8"?>
<entity-facade-xml type="ext-upgrade">
</entity-facade-xml>
```

### oms
**Release tag:** v3.1.8    **Exact file:** upgrade/v3.1.8/UpgradeData.xml    **Type:** XML

```xml
<?xml version="1.0" encoding="UTF-8"?>
<entity-facade-xml type="ext-upgrade">
</entity-facade-xml>
```

### mantle-netsuite-connector
**Release tag:** v3.0.0-RC1    **Exact file:** upgrade/v3.0.0-RC1/UpgradeData.xml    **Type:** XML

```xml
<?xml version="1.0" encoding="UTF-8"?>
<entity-facade-xml type="ext-upgrade">

    <moqui.basic.Enumeration enumId="GEN_CC_ADJ_FEED_NS" enumCode="GEN_CC_ADJ_FEED_NS" description="Generate Cycle Count Adjustment Feed for NetSuite" enumTypeId="INVENTORY_SYS_JOB"/>
    <Product productId="GEN_CC_ADJ_FEED_NS" productTypeId="SERVICE" internalName="GEN_CC_ADJ_FEED_NS"
             productName="Generate Cycle Count Adjustment Feed for NetSuite" description="Generate Cycle Count Adjustment Feed for NetSuite"
             primaryProductCategoryId="INVENTORY_SYS_JOB"/>

    <!-- Template Service Job to generate the Cycle Count Adjustment Feed from HotWax to NetSuite -->
    <moqui.service.job.ServiceJob jobName="Generate_CycleCount_Adjustment_Feed" instanceOfProductId="GEN_CC_ADJ_FEED_NS" jobTypeEnumId="GEN_CC_ADJ_FEED_NS"
        description="Generate Cycle Count Adjustment Feed for NetSuite"
        serviceName="co.hotwax.netsuite.InventoryServices.generate#CycleCountAdjustmentFeed"
        cronExpression="0 0 0 * * ?" paused="Y">
        <parameters parameterName="recordLimitPerFeed" parameterValue="1000"/>
        <parameters parameterName="filePathPattern" parameterValue="netsuite/inventoryadjustment/csv"/>
        <parameters parameterName="systemMessageRemoteId"/>
        <parameters parameterName="jobName" parameterValue="Generate_CycleCount_Adjustment_Feed"/>
        <parameters parameterName="skipLastRunTimeUpdate" parameterValue="false"/>
        <parameters parameterName="lastRunTime"/>
        <parameters parameterName="adjustmentAccount"/>
        <parameters parameterName="memoText"/>
        <parameters parameterName="excludedProductTypeIds" parameterValue="MARKETING_PKG_PICK"/>
        <parameters parameterName="excludedNetsuiteItemIds"/>
        <parameters parameterName="fileNamePrefix"/>
        <parameters parameterName="subsidiary"/>
    </moqui.service.job.ServiceJob>

    <!-- New MDM Configurations for Transfer Orders and Fulfillments -->
    <co.hotwax.datamanager.DataManagerConfig
        configId="NS_TO_IMPORT"
        description="NetSuite Transfer Order Import"
        importServiceName="co.hotwax.netsuite.TransferOrderServices.import#TransferOrder"
        importPath="/home/${sftpUsername}/netsuite/transferorderv2/import/transfer-order"
        executionModeId="DMC_QUEUE"/>

    <co.hotwax.datamanager.DataManagerConfig
        configId="NS_TO_STORE_FULFILL"
        description="NetSuite Store TO Fulfillment Import"
        importServiceName="co.hotwax.poorti.TransferOrderFulfillmentServices.update#TransferOrderShipment"
        importPath="/home/${sftpUsername}/netsuite/transferorderv2/import/fulfillment-store"
        executionModeId="DMC_QUEUE"/>

    <co.hotwax.datamanager.DataManagerConfig
        configId="NS_TO_WH_FULFILL"
        description="NetSuite Warehouse TO Fulfillment Import"
        importServiceName="co.hotwax.netsuite.TransferOrderServices.import#WhToFulfillment"
        importPath="/home/${sftpUsername}/netsuite/transferorderv2/import/fulfillment-wh"
        executionModeId="DMC_QUEUE"/>

    <!-- Job 1: NetSuite Transfer Order Import -->
    <org.apache.ofbiz.product.product.Product productId="IMP_TRANSORD_NS" productTypeId="SERVICE" internalName="IMP_TRANSORD_NS"
             productName="Import NetSuite Transfer Order" description="Import NetSuite Transfer Order"
             primaryProductCategoryId="ORDER_SYS_JOB"/>
    <org.apache.ofbiz.product.category.ProductCategoryMember productId="IMP_TRANSORD_NS" productCategoryId="ORDER_SYS_JOB" fromDate="2024-01-01 00:00:00.0"/>
    <moqui.service.job.ServiceJob jobName="import_NetSuiteTransferOrder"
        description="Import NetSuite Transfer Order"
        serviceName="co.hotwax.util.UtilityServices.get#DataManagerFileFromSftp"
        instanceOfProductId="IMP_TRANSORD_NS" paused="Y">
        <parameters parameterName="configId" parameterValue="NS_TO_IMPORT"/>
        <parameters parameterName="systemMessageRemoteId" parameterValue=""/>
    </moqui.service.job.ServiceJob>

    <!-- Job 2: NetSuite Store TO Fulfillment Import -->
    <org.apache.ofbiz.product.product.Product productId="IMP_TO_STORE_FULFILL" productTypeId="SERVICE" internalName="IMP_TO_STORE_FULFILL"
             productName="Import NetSuite Store Transfer Order Fulfillment" description="Import NetSuite Store Transfer Order Fulfillment"
             primaryProductCategoryId="FULFILLMENT_SYS_JOB"/>
    <org.apache.ofbiz.product.category.ProductCategoryMember productId="IMP_TO_STORE_FULFILL" productCategoryId="FULFILLMENT_SYS_JOB" fromDate="2024-01-01 00:00:00.0"/>
    <org.apache.ofbiz.product.category.ProductCategoryMember productId="IMP_TO_STORE_FULFILL" productCategoryId="IMPORT_SYS_JOB" fromDate="2024-01-01 00:00:00.0"/>
    <moqui.service.job.ServiceJob jobName="import_NetSuiteStoreFulfillment"
        description="Import NetSuite Store Transfer Order Fulfillment"
        serviceName="co.hotwax.util.UtilityServices.get#DataManagerFileFromSftp"
        instanceOfProductId="IMP_TO_STORE_FULFILL" paused="Y">
        <parameters parameterName="configId" parameterValue="NS_TO_STORE_FULFILL"/>
        <parameters parameterName="systemMessageRemoteId" parameterValue=""/>
    </moqui.service.job.ServiceJob>

    <!-- Job 3: NetSuite Warehouse TO Fulfillment Import -->
    <org.apache.ofbiz.product.product.Product productId="IMP_TO_WH_FULFILL" productTypeId="SERVICE" internalName="IMP_TO_WH_FULFILL"
             productName="Import NetSuite Warehouse Transfer Order Fulfillment" description="Import NetSuite Warehouse Transfer Order Fulfillment"
             primaryProductCategoryId="FULFILLMENT_SYS_JOB"/>
    <org.apache.ofbiz.product.category.ProductCategoryMember productId="IMP_TO_WH_FULFILL" productCategoryId="FULFILLMENT_SYS_JOB" fromDate="2024-01-01 00:00:00.0"/>
    <org.apache.ofbiz.product.category.ProductCategoryMember productId="IMP_TO_WH_FULFILL" productCategoryId="IMPORT_SYS_JOB" fromDate="2024-01-01 00:00:00.0"/>
    <moqui.service.job.ServiceJob jobName="import_NetSuiteWhFulfillment"
        description="Import NetSuite Warehouse Transfer Order Fulfillment"
        serviceName="co.hotwax.util.UtilityServices.get#DataManagerFileFromSftp"
        instanceOfProductId="IMP_TO_WH_FULFILL" paused="Y">
        <parameters parameterName="configId" parameterValue="NS_TO_WH_FULFILL"/>
        <parameters parameterName="systemMessageRemoteId" parameterValue=""/>
    </moqui.service.job.ServiceJob>
</entity-facade-xml>
```

### mantle-netsuite-connector
**Release tag:** v3.0.0-RC1    **Exact file:** upgrade/v3.0.0-RC1/UpgradeSql.sql    **Type:** SQL

```sql
-- Drop Foreign Key constraints referencing USER_LOGIN for ProductPromo entity
ALTER TABLE PRODUCT_PROMO DROP FOREIGN KEY PROD_PRMO_CUL;
ALTER TABLE PRODUCT_PROMO DROP FOREIGN KEY PROD_PRMO_LMCUL;
```

### mantle-netsuite-connector
**Release tag:** v3.1.0    **Exact file:** upgrade/v3.1.0/UpgradeData.xml    **Type:** XML

```xml
<?xml version="1.0" encoding="UTF-8"?>
<entity-facade-xml type="ext-upgrade">
    <!-- Data Manager Configuration for NetSuite Order Item Attribute Import -->
    <DataManagerConfig configId="MDM_IMP_ORDER_ITM_ATTR" importPath="/home/${sftpUsername}/netsuite/salesorder/import/orderitemattribute" exportPath="" importServiceName="store#org.apache.ofbiz.order.order.OrderItemAttribute" exportServiceName="" executionModeId="DMC_QUEUE"/>

    <!-- NetSuite Order Item Attribute Import Job -->
    <moqui.basic.Enumeration enumId="IMP_ORD_ITM_ATTR_NS" enumCode="IMP_ORD_ITM_ATTR_NS" description="Import Order Item Attribute from NetSuite" enumTypeId="ORDER_SYS_JOB"/>
    <Product productId="IMP_ORD_ITM_ATTR_NS" productTypeId="SERVICE" internalName="IMP_ORD_ITM_ATTR_NS"
             productName="Import Order Item Attribute from NetSuite" description="Import Order Item Attribute from NetSuite"
             primaryProductCategoryId="ORDER_SYS_JOB"/>
    <ProductCategoryMember productId="IMP_ORD_ITM_ATTR_NS" productCategoryId="ORDER_SYS_JOB" fromDate="2024-01-01 00:00:00.0"/>
    <ProductCategoryMember productId="IMP_ORD_ITM_ATTR_NS" productCategoryId="IMPORT_SYS_JOB" fromDate="2024-01-01 00:00:00.0"/>
    <moqui.service.job.ServiceJob jobName="import_NetSuiteOrderItemAttribute" description="Import Order Item Attribute from NetSuite" instanceOfProductId="IMP_ORD_ITM_ATTR_NS" jobTypeEnumId="IMP_ORD_ITM_ATTR_NS"
        serviceName="co.hotwax.util.UtilityServices.get#DataManagerFileFromSftp" cronExpression="" paused="Y">
        <parameters parameterName="configId" parameterValue="MDM_IMP_ORDER_ITM_ATTR"/>
        <parameters parameterName="systemMessageRemoteId" parameterValue=""/>
        <parameters parameterName="parameters" parameterValue=""/>
    </moqui.service.job.ServiceJob>
    <!-- Data Manager Configuration for NetSuite Order Attribute Import -->
    <DataManagerConfig configId="MDM_IMP_ORDER_ATTR" importPath="/home/${sftpUsername}/netsuite/salesorder/import/orderattribute" exportPath="" importServiceName="store#org.apache.ofbiz.order.order.OrderAttribute" exportServiceName="" executionModeId="DMC_QUEUE"/>

    <!-- NetSuite Order Attribute Import Job -->
    <moqui.basic.Enumeration enumId="IMP_ORD_ATTR_NS" enumCode="IMP_ORD_ATTR_NS" description="Import Order Attribute from NetSuite" enumTypeId="ORDER_SYS_JOB"/>
    <Product productId="IMP_ORD_ATTR_NS" productTypeId="SERVICE" internalName="IMP_ORD_ATTR_NS"
             productName="Import Order Attribute from NetSuite" description="Import Order Attribute from NetSuite"
             primaryProductCategoryId="ORDER_SYS_JOB"/>
    <ProductCategoryMember productId="IMP_ORD_ATTR_NS" productCategoryId="ORDER_SYS_JOB" fromDate="2024-01-01 00:00:00.0"/>
    <ProductCategoryMember productId="IMP_ORD_ATTR_NS" productCategoryId="IMPORT_SYS_JOB" fromDate="2024-01-01 00:00:00.0"/>
    <moqui.service.job.ServiceJob jobName="import_NetSuiteOrderAttribute" description="Import Order Attribute from NetSuite" instanceOfProductId="IMP_ORD_ATTR_NS" jobTypeEnumId="IMP_ORD_ATTR_NS"
        serviceName="co.hotwax.util.UtilityServices.get#DataManagerFileFromSftp" cronExpression="" paused="Y">
        <parameters parameterName="configId" parameterValue="MDM_IMP_ORDER_ATTR"/>
        <parameters parameterName="systemMessageRemoteId" parameterValue=""/>
        <parameters parameterName="parameters" parameterValue=""/>
    </moqui.service.job.ServiceJob>

    <!-- Data Manager Configuration for NetSuite Product Facility Inventory Reset Import -->
    <co.hotwax.datamanager.DataManagerConfig
        configId="MDM_NS_IMP_RESET_INV"
        importPath="/home/${sftpUsername}/netsuite/inventoryitem/csv"
        exportPath="" importServiceName="co.hotwax.poorti.FulfillmentServices.reset#ProductFacilityInventory"
        exportServiceName=""
        executionModeId="DMC_QUEUE"/>

    <!-- NetSuite Product Facility Inventory Reset Import Job -->
    <moqui.basic.Enumeration enumId="IMP_PROD_FAC_INV_NS" enumCode="IMP_PROD_FAC_INV_NS" description="Import Product Facility Inventory Reset from NetSuite" enumTypeId="INVENTORY_SYS_JOB"/>
    <Product productId="IMP_PROD_FAC_INV_NS" productTypeId="SERVICE" internalName="IMP_PROD_FAC_INV_NS"
             productName="Import Product Facility Inventory Reset from NetSuite" description="Import Product Facility Inventory Reset from NetSuite"
             primaryProductCategoryId="INVENTORY_SYS_JOB"/>
    <ProductCategoryMember productId="IMP_PROD_FAC_INV_NS" productCategoryId="INVENTORY_SYS_JOB" fromDate="2024-01-01 00:00:00.0"/>
    <moqui.service.job.ServiceJob jobName="import_NetSuiteInventoryReset" description="Import Product Facility Inventory Reset from NetSuite" instanceOfProductId="IMP_PROD_FAC_INV_NS" jobTypeEnumId="IMP_PROD_FAC_INV_NS"
        serviceName="co.hotwax.util.UtilityServices.get#DataManagerFileFromSftp" cronExpression="" paused="Y">
        <parameters parameterName="configId" parameterValue="MDM_NS_IMP_RESET_INV"/>
        <parameters parameterName="systemMessageRemoteId" parameterValue=""/>
        <parameters parameterName="parameters" parameterValue=""/>
    </moqui.service.job.ServiceJob>

    <!-- GOR-375: Replace time-based state tracking with batch ID state tracking for Inventory Reset CSVs -->
    <moqui.service.job.ServiceJobParameter jobName="Generate_Inventory_Var_Feed" parameterName="skipLastProcessedUpdate" parameterValue="false"/>
    <moqui.service.job.ServiceJobParameter jobName="Generate_Inventory_Var_Feed" parameterName="lastProcessedResourceId"/>

    <!-- Enumeration for NetSuite Product ERP ID Import -->
    <moqui.basic.Enumeration enumId="IMP_PROD_IDS_NS" enumCode="IMP_PROD_IDS_NS" description="Import Product ERP IDs from NetSuite" enumTypeId="PRODUCT_SYS_JOB"/>

    <!-- Product for NetSuite Product ERP ID Import -->
    <Product productId="IMP_PROD_IDS_NS" productTypeId="SERVICE" internalName="IMP_PROD_IDS_NS"
             productName="Import Product ERP IDs from NetSuite" description="Import Product ERP IDs from NetSuite"
             primaryProductCategoryId="PRODUCT_SYS_JOB"/>

    <!-- Product Category Member for NetSuite Product ERP ID Import -->
    <ProductCategoryMember productId="IMP_PROD_IDS_NS" productCategoryId="PRODUCT_SYS_JOB" fromDate="2024-01-01 00:00:00.0"/>

    <!-- Service Job for NetSuite Product ERP ID Import -->
    <moqui.service.job.ServiceJob jobName="import_NetSuiteProductIds" description="Import Product ERP IDs from NetSuite" instanceOfProductId="IMP_PROD_IDS_NS" jobTypeEnumId="IMP_PROD_IDS_NS"
        serviceName="co.hotwax.util.UtilityServices.get#DataManagerFileFromSftp" cronExpression="" paused="Y">
        <parameters parameterName="configId" parameterValue="MDM_IMP_PROD_IDENT"/>
        <parameters parameterName="systemMessageRemoteId" parameterValue=""/>
        <parameters parameterName="parameters" parameterValue=""/>
    </moqui.service.job.ServiceJob>

    <!-- Data Manager Configuration for NetSuite Product ERP ID Import -->
    <DataManagerConfig configId="MDM_IMP_PROD_IDENT" importPath="/home/${sftpUsername}/netsuite/product/csv" exportPath="" importServiceName="co.hotwax.oms.product.ProductServices.store#ProductIdentification" exportServiceName="" executionModeId="DMC_QUEUE"/>

    <!-- facilityGroupId/fulfillmentTag are new client-configurable parameters on the existing
         generate_FulfilledOrderItemsFeed_Netsuite template ServiceJob - see upgradeSteps.md -->
    <moqui.service.job.ServiceJob jobName="generate_FulfilledOrderItemsFeed_Netsuite">
        <parameters parameterName="facilityGroupId"/>
        <parameters parameterName="fulfillmentTag"/>
    </moqui.service.job.ServiceJob>

    <!-- Parent EnumerationType, must exist before any Enumeration with enumTypeId="NETSUITE" -->
    <moqui.basic.EnumerationType enumTypeId="NETSUITE" description="NetSuite Integration Type"/>
    <moqui.basic.Enumeration description="NetSuite Sales Order Internal Id" enumCode="NETSUITE_ORDER_ID" enumId="NETSUITE_ORDER_ID" enumTypeId="ORDER_IDENTITY" sequenceNum="2"/>
    <org.apache.ofbiz.product.product.GoodIdentificationType goodIdentificationTypeId="NETSUITE_PRODUCT_ID" parentTypeId="HC_GOOD_ID_TYPE" hasTable="N" description="NetSuite Product Internal Id"/>
    <moqui.basic.Enumeration enumId="NETSUITE_PRICE_LEVEL" enumTypeId="NETSUITE" description="NetSuite Price Level"/>

    <moqui.basic.Enumeration enumId="RG_NS_ORDER_PUSH" description="Netsuite Order Push" sequenceNum="30" enumTypeId="ATP_RULE_GROUP_TYPE" enumCode="RG_NS_ORDER_PUSH"/>

    <moqui.basic.Enumeration enumId="GEN_TO_ITEM_CNCL_FD" enumCode="GEN_TO_ITEM_CNCL_FD" description="Generate Transfer Order Item Cancellation Feed" enumTypeId="ORDER_SYS_JOB"/>

    <Product productId="GEN_TO_ITEM_CNCL_FD" productTypeId="SERVICE" internalName="GEN_TO_ITEM_CNCL_FD"
        productName="Generate Transfer Order Item Cancellation Feed" description="Generate Transfer Order Item Cancellation Feed"
        primaryProductCategoryId="ORDER_SYS_JOB"/>

    <ProductCategoryMember productId="GEN_TO_ITEM_CNCL_FD" productCategoryId="ORDER_SYS_JOB" fromDate="2024-01-01 00:00:00.0"/>

    <moqui.service.job.ServiceJob jobName="generate_TO_Item_Cancellation_Feed" instanceOfProductId="GEN_TO_ITEM_CNCL_FD" jobTypeEnumId="GEN_TO_ITEM_CNCL_FD"
        description="Service to generate feed file for NetSuite to close cancelled Store-to-Store Transfer Order items"
        serviceName="co.hotwax.netsuite.TransferOrderServices.generate#CancelledTransferOrderItemsFeed"
        cronExpression="0 0/15 * * * ?" paused="Y">
        <parameters parameterName="systemMessageRemoteId"/>
        <parameters parameterName="filePathPattern" parameterValue="netsuite/transferorderv2/update"/>
        <parameters parameterName="orderId"/>
        <parameters parameterName="cancelledDate"/>
        <parameters parameterName="recordLimitPerFeed" parameterValue="1000"/>
        <parameters parameterName="jobName" parameterValue="Generate_TO_Item_Cancellation_Feed"/>
        <parameters parameterName="skipLastRunTimeUpdate" parameterValue="false"/>
        <parameters parameterName="lastRunTime"/>
    </moqui.service.job.ServiceJob>

    <!-- Transfer Order Update Configuration -->
    <co.hotwax.datamanager.DataManagerConfig
        configId="NS_TO_UPDATE"
        description="NetSuite Transfer Order Update Import"
        importServiceName="co.hotwax.netsuite.TransferOrderServices.update#TransferOrder"
        importPath="/home/${sftpUsername}/netsuite/transferorderv2/import/transfer-order/update"
        executionModeId="DMC_QUEUE"/>
  <org.apache.ofbiz.product.product.Product productId="UPD_TRANSORD_NS" productTypeId="SERVICE" internalName="UPD_TRANSORD_NS"
                                              productName="Update NetSuite Transfer Order" description="Update NetSuite Transfer Order"
                                              primaryProductCategoryId="ORDER_SYS_JOB"/>
    <org.apache.ofbiz.product.category.ProductCategoryMember productId="UPD_TRANSORD_NS" productCategoryId="ORDER_SYS_JOB" fromDate="2024-01-01 00:00:00.0"/>
    <moqui.service.job.ServiceJob jobName="update_NetSuiteTransferOrder"
        description="Adds new line items and updated line quantities to existing Transfer Orders"
        serviceName="co.hotwax.util.UtilityServices.get#DataManagerFileFromSftp"
        instanceOfProductId="UPD_TRANSORD_NS" paused="Y">
        <parameters parameterName="configId" parameterValue="NS_TO_UPDATE"/>
    </moqui.service.job.ServiceJob>
    <!-- Data Manager Configuration for NetSuite Warehouse Order Item Fulfillment Feed -->
    <co.hotwax.datamanager.DataManagerConfig configId="IMP_NS_SO_WH_FLFLMNT" importPath="/home/${sftpUsername}/netsuite/salesorder/import/fulfillment" importServiceName="co.hotwax.netsuite.OrderServices.import#WarehouseOrderFulfillment" description="Import NetSuite Warehouse Order Item Fulfillment Feed" executionModeId="DMC_QUEUE"/>

    <!-- Product for NetSuite Warehouse Order Item Fulfillment Feed -->
    <org.apache.ofbiz.product.product.Product productId="IMP_NS_SO_WH_FLFLMNT" productTypeId="SERVICE" internalName="IMP_NS_SO_WH_FLFLMNT"
             productName="Import NetSuite Warehouse Order Item Fulfillment Feed" description="Import NetSuite Warehouse Order Item Fulfillment Feed"
             primaryProductCategoryId="FULFILLMENT_SYS_JOB"/>

    <!-- Product Category Members for NetSuite Warehouse Order Item Fulfillment Feed -->
    <org.apache.ofbiz.product.category.ProductCategoryMember productId="IMP_NS_SO_WH_FLFLMNT" productCategoryId="FULFILLMENT_SYS_JOB" fromDate="2024-01-01 00:00:00.0"/>
    <org.apache.ofbiz.product.category.ProductCategoryMember productId="IMP_NS_SO_WH_FLFLMNT" productCategoryId="IMPORT_SYS_JOB" fromDate="2024-01-01 00:00:00.0"/>

    <!-- Service Job for NetSuite Warehouse Order Item Fulfillment Feed -->
    <moqui.service.job.ServiceJob jobName="import_NS_SO_WH_Fulfillment" description="Import NetSuite Warehouse Order Item Fulfillment Feed" instanceOfProductId="IMP_NS_SO_WH_FLFLMNT" jobTypeEnumId="IMP_NS_SO_WH_FLFLMNT"
        serviceName="co.hotwax.util.UtilityServices.get#DataManagerFileFromSftp" cronExpression="0 0/15 * * * ?" paused="Y">
        <parameters parameterName="configId" parameterValue="IMP_NS_SO_WH_FLFLMNT"/>
        <parameters parameterName="systemMessageRemoteId" parameterValue=""/>
        <parameters parameterName="parameters" parameterValue=""/>
    </moqui.service.job.ServiceJob>
    <!-- NetSuite Job Product Data -->
    <org.apache.ofbiz.product.product.Product productId="GEN_CD_FEED_NS" productTypeId="SERVICE" internalName="GEN_CD_FEED_NS"
             productName="Generate Customer Deposit Feed for NetSuite" description="Generate Customer Deposit Feed for NetSuite"
             primaryProductCategoryId="ORDER_SYS_JOB"/>
    <org.apache.ofbiz.product.category.ProductCategoryMember productId="GEN_CD_FEED_NS" productCategoryId="ORDER_SYS_JOB" fromDate="2026-01-01 00:00:00.0"/>

    <!-- Template Service Job to generate Customer Deposit Feed from HotWax to NetSuite -->
    <moqui.service.job.ServiceJob jobName="generate_CustomerDepositFeedV2" instanceOfProductId="GEN_CD_FEED_NS"
        description="Generate Customer Deposit Feed for NetSuite"
        serviceName="co.hotwax.netsuite.CustomerDepositServices.generate#CustomerDepositFeedV2"
        cronExpression="0 0/15 * * * ?" paused="Y">
        <parameters parameterName="systemMessageTypeId" parameterValue="GenerateCustomerDepositFeed"/>
        <parameters parameterName="systemMessageRemoteId"/>
        <parameters parameterName="excludePaymentMethodType"/>
        <parameters parameterName="excludeCancelledOrders" parameterValue="Y"/>
        <parameters parameterName="lastFromDate"/>
    </moqui.service.job.ServiceJob>

    <!-- Transfer Order Receipt Import Configuration -->
    <co.hotwax.datamanager.DataManagerConfig
        configId="NS_TO_RECEIPT_IMPORT"
        description="NetSuite Transfer Order Receipt Import"
        importServiceName="co.hotwax.netsuite.TransferOrderServices.import#TransferOrderReceipt"
        importPath="/home/${sftpUsername}/netsuite/transferorderv2/import/receipt"
        executionModeId="DMC_QUEUE"/>

    <!-- NetSuite Transfer Order Receipt Import Job -->
    <moqui.basic.Enumeration enumId="IMP_TO_RCPT_NS" enumCode="IMP_TO_RCPT_NS" description="Import Transfer Order Receipt from NetSuite" enumTypeId="FULFILLMENT_SYS_JOB"/>
    <org.apache.ofbiz.product.product.Product productId="IMP_TO_RCPT_NS" productTypeId="SERVICE" internalName="IMP_TO_RCPT_NS"
             productName="Import Transfer Order Receipt from NetSuite" description="Import Transfer Order Receipt from NetSuite"
             primaryProductCategoryId="FULFILLMENT_SYS_JOB"/>
    <org.apache.ofbiz.product.category.ProductCategoryMember productId="IMP_TO_RCPT_NS" productCategoryId="FULFILLMENT_SYS_JOB" fromDate="2026-01-01 00:00:00.0"/>
    <org.apache.ofbiz.product.category.ProductCategoryMember productId="IMP_TO_RCPT_NS" productCategoryId="IMPORT_SYS_JOB" fromDate="2026-01-01 00:00:00.0"/>
    <moqui.service.job.ServiceJob jobName="import_NetSuiteTransferOrderReceipt" description="Import Transfer Order Receipt from NetSuite"
        instanceOfProductId="IMP_TO_RCPT_NS" jobTypeEnumId="IMP_TO_RCPT_NS"
        serviceName="co.hotwax.util.UtilityServices.get#DataManagerFileFromSftp" paused="Y">
        <parameters parameterName="configId" parameterValue="NS_TO_RECEIPT_IMPORT"/>
        <parameters parameterName="systemMessageRemoteId" parameterValue=""/>
    </moqui.service.job.ServiceJob>

    <!-- Customer Refund Feed for NetSuite -->

    <moqui.basic.Enumeration enumId="GEN_CR_FEED_NS"
            enumCode="GEN_CR_FEED_NS"
            description="Generate Customer Refund Feed for Netsuite"
            enumTypeId="ORDER_SYS_JOB"/>

    <org.apache.ofbiz.product.product.Product productId="GEN_CR_FEED_NS"
            productTypeId="SERVICE"
            internalName="GEN_CR_FEED_NS"
            productName="Generate Customer Refund Feed for NetSuite"
            description="Generate Customer Refund Feed for NetSuite"
            primaryProductCategoryId="ORDER_SYS_JOB"/>

    <org.apache.ofbiz.product.category.ProductCategoryMember productId="GEN_CR_FEED_NS"
            productCategoryId="ORDER_SYS_JOB"
            fromDate="2024-01-01 00:00:00.0"/>

    <moqui.service.message.SystemMessageType systemMessageTypeId="GenerateCustomerRefundFeed"
            description="Generate customer deposit Refund feed from hotwax to Netsuite"
            parentTypeId="LocalFeedFile"
            sendPath="/home/${sftpUsername}/netsuite/salesorder/customer-refund/CustomerDepositRefundFeed-${systemMessageId}-${dateTime}.json"
            sendServiceName="co.hotwax.ofbiz.SystemMessageServices.send#SystemMessageFileSftp"
            receivePath="${contentRoot}/customerRefund/customerRefundDepositFeed-${dateTime}.json"/>

    <moqui.service.job.ServiceJob jobName="generate_CustomerRefundFeed"
            instanceOfProductId="GEN_CR_FEED_NS"
            jobTypeEnumId="GEN_CR_FEED_NS"
            description="Generate Customer Refund Feed for NetSuite"
            serviceName="co.hotwax.netsuite.CustomerDepositServices.generate#CustomerRefundFeed"
            cronExpression="0 0/15 * * * ?"
            paused="Y">
        <parameters parameterName="systemMessageTypeId" parameterValue="GenerateCustomerRefundFeed"/>
        <parameters parameterName="systemMessageRemoteId"/>
        <parameters parameterName="bufferTime" parameterValue="0"/>
        <parameters parameterName="lastFromDate"/>
        <parameters parameterName="excludePaymentMethodType"/>
        <parameters parameterName="includePaymentMethodType"/>
    </moqui.service.job.ServiceJob>
    <moqui.basic.Enumeration enumId="GEN_INV_DMG_FEED_NS" enumCode="GEN_INV_DMG_FEED_NS" description="Generate Inventory Transfer Damage Location Feed for NetSuite" enumTypeId="INVENTORY_SYS_JOB"/>
    <Product productId="GEN_INV_DMG_FEED_NS" productTypeId="SERVICE" internalName="GEN_INV_DMG_FEED_NS"
             productName="Generate Inventory Transfer Damage Location Feed for NetSuite" description="Generate Inventory Transfer Damage Location Feed for NetSuite"
             primaryProductCategoryId="INVENTORY_SYS_JOB"/>
    <ProductCategoryMember productId="GEN_INV_DMG_FEED_NS" productCategoryId="INVENTORY_SYS_JOB" fromDate="2001-01-01 00:00:00.0"/>
    <!-- Template Service Job to generate the Inventory Transfer Damage Location Feed from HotWax to NetSuite -->
    <moqui.service.job.ServiceJob jobName="generate_InventoryTransferDamageLocFeed" instanceOfProductId="GEN_INV_DMG_FEED_NS" jobTypeEnumId="GEN_INV_DMG_FEED_NS"
                                  description="Generate Inventory Transfer Feed for Damage Location for NetSuite"
                                  serviceName="co.hotwax.netsuite.InventoryServices.generate#InventoryTransferDamageLocFeed"
                                  cronExpression="0 8/15 * * * ?" paused="Y">
        <parameters parameterName="recordLimitPerFeed" parameterValue="1000"/>
        <parameters parameterName="filePathPattern" parameterValue="netsuite/inventorytransfer/csv"/>
        <parameters parameterName="systemMessageRemoteId"/>
        <parameters parameterName="jobName" parameterValue="generate_InventoryTransferDamageLocFeed"/>
        <parameters parameterName="skipLastRunTimeUpdate" parameterValue="false"/>
        <parameters parameterName="lastRunTime"/>
        <parameters parameterName="fileNamePrefix" parameterValue="Inventory_tranfer_Feed_"/>
    </moqui.service.job.ServiceJob>

    <org.apache.ofbiz.party.party.RoleType roleTypeId="DEFAULT_DEPARTMENT" hasTable="N" description="Default Department"/>

    <!-- Data Manager Configuration for NetSuite Inventory Adjustment / Delta Import -->
    <co.hotwax.datamanager.DataManagerConfig
        configId="NS_IMP_INV_DELTA"
        description="NetSuite Inventory Adjustment Import"
        importPath="/home/${sftpUsername}/netsuite/inventoryadjustment/import"
        importServiceName="co.hotwax.poorti.FulfillmentServices.adjust#InventoryDeltaByIdentification"
        executionModeId="DMC_QUEUE"/>

    <!-- NetSuite Inventory Adjustment / Delta Import Job -->
    <moqui.basic.Enumeration enumId="IMP_INV_DELTA_NS" enumCode="IMP_INV_DELTA_NS" description="Import Inventory Adjustments from NetSuite" enumTypeId="INVENTORY_SYS_JOB"/>
    <org.apache.ofbiz.product.product.Product productId="IMP_INV_DELTA_NS" productTypeId="SERVICE" internalName="IMP_INV_DELTA_NS"
             productName="Import Inventory Adjustments from NetSuite" description="Import Inventory Adjustments from NetSuite"
             primaryProductCategoryId="INVENTORY_SYS_JOB"/>
    <org.apache.ofbiz.product.category.ProductCategoryMember productId="IMP_INV_DELTA_NS" productCategoryId="INVENTORY_SYS_JOB" fromDate="2024-01-01 00:00:00.0"/>
    <moqui.service.job.ServiceJob jobName="import_NetSuiteInventoryDelta" description="Import Inventory Adjustments from NetSuite" instanceOfProductId="IMP_INV_DELTA_NS" jobTypeEnumId="IMP_INV_DELTA_NS"
        serviceName="co.hotwax.util.UtilityServices.get#DataManagerFileFromSftp" cronExpression="0 0/15 * * * ?" paused="Y">
        <parameters parameterName="configId" parameterValue="NS_IMP_INV_DELTA"/>
        <parameters parameterName="systemMessageRemoteId" parameterValue=""/>
    </moqui.service.job.ServiceJob>

    <!-- System Message Type -->
    <moqui.service.message.SystemMessageType systemMessageTypeId="GenerateOrderCancellationFeed"
         description="Generate Order Cancellation Feed from HotWax to NetSuite"
         parentTypeId="LocalFeedFile"
         sendPath="/home/${sftpUsername}/netsuite/cancellation/CreateCancellationFeed-${productStoreId}-${systemMessageId}-${dateTime}.csv"
         sendServiceName="co.hotwax.ofbiz.SystemMessageServices.send#SystemMessageFileSftp"
         receivePath="runtime://datamanager/netsuite/cancellation/CreateCancellationFeed-${feedType}-${dateTime}.csv"/>

    <!-- Enumerations -->
    <moqui.basic.Enumeration enumId="GEN_ITEM_CANCEL_FD" enumCode="GEN_ITEM_CANCEL_FD" description="Generate Item Cancellation Feed for NetSuite" enumTypeId="ORDER_SYS_JOB"/>
    <moqui.basic.Enumeration enumId="GEN_ORDER_CANCEL_FD" enumCode="GEN_ORDER_CANCEL_FD" description="Generate Order Cancellation Feed for NetSuite" enumTypeId="ORDER_SYS_JOB"/>

    <!-- Template Service Jobs -->
    <moqui.service.job.ServiceJob jobName="generate_ItemCancellationFeed" jobTypeEnumId="GEN_ITEM_CANCEL_FD"
           description="Template Service Job to generate Item Cancellation Feed from HotWax"
           serviceName="co.hotwax.netsuite.OrderServices.generate#NetSuiteItemCancellationFeed"
           transactionTimeout="7200" cronExpression="0 0 * * * ?" paused="Y">
        <parameters parameterName="systemMessageTypeId" parameterValue="GenerateOrderCancellationFeed"/>
        <parameters parameterName="systemMessageRemoteId"/>
        <parameters parameterName="lastSyncTime"/>
        <parameters parameterName="itemAttrNames" parameterValue="['NetsuiteItemLineId', 'NetsuiteDiscountItemLineId']"/>
    </moqui.service.job.ServiceJob>

    <moqui.service.job.ServiceJob jobName="generate_OrderCancellationFeed" jobTypeEnumId="GEN_ORDER_CANCEL_FD"
           description="Template Service Job to generate Order Cancellation Feed from HotWax"
           serviceName="co.hotwax.netsuite.OrderServices.generate#NetSuiteOrderCancellationFeed"
           transactionTimeout="7200" cronExpression="0 0 * * * ?" paused="Y">
        <parameters parameterName="systemMessageTypeId" parameterValue="GenerateOrderCancellationFeed"/>
        <parameters parameterName="systemMessageRemoteId"/>
        <parameters parameterName="lastSyncTime"/>
        <parameters parameterName="orderAttrNames" parameterValue="['NETSUITE_PAYMENT_LINE_ID', 'NETSUITE_VARIANCE_LINE_ID']"/>
    </moqui.service.job.ServiceJob>

    <co.hotwax.datamanager.DataManagerConfig
        configId="NS_TO_WH_CANCEL_ITEM"
        description="NetSuite Warehouse Transfer Order Item Close Import"
        importServiceName="co.hotwax.netsuite.TransferOrderServices.import#CancelledWhTransferOrderItems"
        importPath="/home/${sftpUsername}/netsuite/transferorderv2/import/transfer-order-close-wh"
        executionModeId="DMC_QUEUE"/>

    <moqui.service.job.ServiceJob jobName="import_NetSuiteWhTransferOrderCancellation"
        serviceName="co.hotwax.util.UtilityServices.get#DataManagerFileFromSftp" paused="Y">
        <parameters parameterName="configId" parameterValue="NS_TO_WH_CANCEL_ITEM"/>
        <parameters parameterName="systemMessageRemoteId" parameterValue=""/>
    </moqui.service.job.ServiceJob>
    <!-- Service Job Data to generate inventory adjustment variances feed for NetSuite -->
    <moqui.basic.Enumeration enumId="GEN_INV_ADJ_FEED_NS" enumCode="GEN_INV_ADJ_FEED_NS" description="Generate HotWax Inventory Adjustments to NetSuite" enumTypeId="INVENTORY_SYS_JOB"/>
    <Product productId="GEN_INV_ADJ_FEED_NS" productTypeId="SERVICE" internalName="GEN_INV_ADJ_FEED_NS"
             productName="Generate HotWax Inventory Adjustments to NetSuite" description="Generate HotWax Inventory Adjustments to NetSuite"
             primaryProductCategoryId="INVENTORY_SYS_JOB"/>
    <ProductCategoryMember productId="GEN_INV_ADJ_FEED_NS" productCategoryId="INVENTORY_SYS_JOB" fromDate="2024-01-01 00:00:00.0"/>
    <moqui.service.job.ServiceJob jobName="generate_InventoryAdjustmentFeedToNetSuite" instanceOfProductId="GEN_INV_ADJ_FEED_NS" jobTypeEnumId="GEN_INV_ADJ_FEED_NS"
                                  description="Generate HotWax Inventory Adjustments to NetSuite"
                                  serviceName="co.hotwax.netsuite.InventoryServices.generate#InventoryAdjustmentFeedToNetSuite"
                                  cronExpression="0 0 0 * * ?" paused="Y">
        <parameters parameterName="systemMessageRemoteId"/>
        <parameters parameterName="jobName" parameterValue="generate_InventoryAdjustmentFeedToNetSuite"/>
        <parameters parameterName="fileNamePrefix"/>
        <parameters parameterName="lastRunTime"/>
        <parameters parameterName="sinceDate"/>
        <parameters parameterName="adjustmentAccount"/>
    </moqui.service.job.ServiceJob>

</entity-facade-xml>
```

### mantle-netsuite-connector
**Release tag:** v3.1.0    **Exact file:** upgrade/v3.1.0/UpgradeSql.sql    **Type:** SQL

```sql
-- GOR-375: Remove deprecated time-based state tracking parameters for Inventory Reset CSVs
DELETE FROM SERVICE_JOB_PARAMETER WHERE JOB_NAME = 'Generate_Inventory_Var_Feed' AND PARAMETER_NAME = 'lastRunTime';
DELETE FROM SERVICE_JOB_PARAMETER WHERE JOB_NAME = 'Generate_Inventory_Var_Feed' AND PARAMETER_NAME = 'skipLastRunTimeUpdate';
```

### mantle-netsuite-connector
**Release tag:** v3.1.1    **Exact file:** upgrade/v3.1.1/UpgradeData.xml    **Type:** XML

```xml
<?xml version="1.0" encoding="UTF-8"?>
<entity-facade-xml type="ext-upgrade">
</entity-facade-xml>
```

### mantle-netsuite-connector
**Release tag:** v3.1.2    **Exact file:** upgrade/v3.1.2/UpgradeData.xml    **Type:** XML

```xml
<?xml version="1.0" encoding="UTF-8"?>
<entity-facade-xml type="ext-upgrade">
</entity-facade-xml>
```

### mantle-netsuite-connector
**Release tag:** v3.1.3    **Exact file:** upgrade/v3.1.3/UpgradeData.xml    **Type:** XML

```xml
<?xml version="1.0" encoding="UTF-8"?>
<entity-facade-xml type="ext-upgrade">
    <!-- Point the NetSuite product id import at the connector's wrapper service. Same in-parameters as
         co.hotwax.oms.product.ProductServices.store#ProductIdentification, so the feed file is unchanged;
         the wrapper additionally creates a blanket variant product when the NetSuite item has not reached
         OMS from Shopify yet, instead of failing the row. Only importServiceName changes here — the other
         DataManagerConfig fields are left off so an existing row keeps its configured paths. -->
    <DataManagerConfig configId="MDM_IMP_PROD_IDENT" importServiceName="co.hotwax.netsuite.ProductServices.store#NetSuiteProductIdentification"/>
</entity-facade-xml>
```

### mantle-netsuite-connector
**Release tag:** v3.1.4    **Exact file:** upgrade/v3.1.4/UpgradeData.xml    **Type:** XML

```xml
<?xml version="1.0" encoding="UTF-8"?>
<entity-facade-xml type="ext-upgrade">
</entity-facade-xml>
```

### mantle-netsuite-connector
**Release tag:** v3.1.5    **Exact file:** upgrade/v3.1.5/UpgradeData.xml    **Type:** XML

```xml
<?xml version="1.0" encoding="UTF-8"?>
<entity-facade-xml type="ext-upgrade">
</entity-facade-xml>
```

### OrderRouting
**Release tag:** v2.0.0-RC1    **Exact file:** upgrade/v2.0.0-RC1/UpgradeData.xml    **Type:** XML

```xml
<?xml version="1.0" encoding="UTF-8"?>
<entity-facade-xml type="ext-upgrade">
</entity-facade-xml>
```

### OrderRouting
**Release tag:** v2.1.0    **Exact file:** upgrade/v2.1.0/UpgradeData.xml    **Type:** XML

```xml
<?xml version="1.0" encoding="UTF-8"?>
<entity-facade-xml type="ext-upgrade">
    <!-- ORDER_ROUTING_API authorizations for the application user groups, moved here from
         component://oms/data/DH_ExtSeed_UserPermissionData.xml so they live with the artifact group. -->
    <artifactGroups artifactGroupId="ORDER_ROUTING_API" description="Commerce Order Routing API (via root resource)">
        <artifacts artifactTypeEnumId="AT_REST_PATH" inheritAuthz="Y" artifactName="/order-routing"/>
        <!-- Full permissions for the ADMIN user group -->
        <authz artifactAuthzId="ORDER_ROUTING_API_ADMIN" userGroupId="ADMIN" authzTypeEnumId="AUTHZT_ALWAYS" authzActionEnumId="AUTHZA_ALL"/>
        <!-- Full permissions for the application user groups -->
        <authz artifactAuthzId="ORDER_ROUTING_API_CSR" userGroupId="CSR" authzTypeEnumId="AUTHZT_ALWAYS" authzActionEnumId="AUTHZA_ALL"/>
        <authz artifactAuthzId="ORDER_ROUTING_API_OM" userGroupId="ORDER_MANAGER" authzTypeEnumId="AUTHZT_ALWAYS" authzActionEnumId="AUTHZA_ALL"/>
    </artifactGroups>
</entity-facade-xml>
```

### hotwax-ofbiz-oms-usl
**Release tag:** v4.0.0-RC1    **Exact file:** upgrade/v4.0.0-RC1/UpgradeData.xml    **Type:** XML

```xml
<?xml version="1.0" encoding="UTF-8"?>
<entity-facade-xml type="ext-upgrade">
</entity-facade-xml>
```

### hotwax-ofbiz-oms-usl
**Release tag:** v4.1.0    **Exact file:** upgrade/v4.1.0/UpgradeData.xml    **Type:** XML

```xml
<?xml version="1.0" encoding="UTF-8"?>
<entity-facade-xml type="ext-upgrade">
    <!-- ADMIN_API authorizations for the application user groups, moved here from
         component://oms/data/DH_ExtSeed_UserPermissionData.xml so they live with the artifact group. -->
    <artifactGroups artifactGroupId="ADMIN_API" description="Commerce Admin API (via root resource)">
        <artifacts artifactTypeEnumId="AT_REST_PATH" inheritAuthz="Y" artifactName="/admin"/>
        <!-- Full permissions for the ADMIN user group -->
        <authz artifactAuthzId="ADMIN_API" userGroupId="ADMIN" authzTypeEnumId="AUTHZT_ALWAYS" authzActionEnumId="AUTHZA_ALL"/>
        <!-- Full permissions for the application user groups -->
        <authz artifactAuthzId="ADMIN_API_SM" userGroupId="STORE_MANAGER" authzTypeEnumId="AUTHZT_ALWAYS" authzActionEnumId="AUTHZA_ALL"/>
        <authz artifactAuthzId="ADMIN_API_WM" userGroupId="WAREHOUSE_MANAGER" authzTypeEnumId="AUTHZT_ALWAYS" authzActionEnumId="AUTHZA_ALL"/>
        <authz artifactAuthzId="ADMIN_API_CSR" userGroupId="CSR" authzTypeEnumId="AUTHZT_ALWAYS" authzActionEnumId="AUTHZA_ALL"/>
        <authz artifactAuthzId="ADMIN_API_OM" userGroupId="ORDER_MANAGER" authzTypeEnumId="AUTHZT_ALWAYS" authzActionEnumId="AUTHZA_ALL"/>
        <authz artifactAuthzId="ADMIN_API_MM" userGroupId="MERCHANDISE_MGR" authzTypeEnumId="AUTHZT_ALWAYS" authzActionEnumId="AUTHZA_ALL"/>
    </artifactGroups>
</entity-facade-xml>
```

### hotwax-poorti
**Release tag:** v3.0.0-RC1    **Exact file:** upgrade/v3.0.0-RC1/UpgradeData.xml    **Type:** XML

```xml
<?xml version="1.0" encoding="UTF-8"?>
<entity-facade-xml type="ext-upgrade">
    <org.apache.ofbiz.party.communication.CommunicationEventType communicationEventTypeId="FULFILLMENT_ERROR" hasTable="N" description="Fulfillment Error" contactMechTypeId="INTERNAL_PARTYID"/>
</entity-facade-xml>
```

### hotwax-poorti
**Release tag:** v3.0.0-RC1    **Exact file:** upgrade/v3.0.0-RC1/UpgradeSql.sql    **Type:** SQL

```sql
-- Drop Foreign Key constraints referencing USER_LOGIN for Poorti / Inventory Count entities
ALTER TABLE INV_COUNT_IMPORT_STATUS DROP FOREIGN KEY INV_CNT_STTS_USRLN;
ALTER TABLE INVENTORY_COUNT_IMPORT_LOCK DROP FOREIGN KEY INV_CNT_IMP_LOCK_USER;
ALTER TABLE INVENTORY_COUNT_IMPORT_LOCK DROP FOREIGN KEY INV_CNT_IMP_LOCK_OVRD_BY;
ALTER TABLE INVENTORY_COUNT_IMPORT_LOCK DROP FOREIGN KEY inventory_count_import_lock_ibfk_2;
ALTER TABLE INVENTORY_COUNT_IMPORT_LOCK DROP FOREIGN KEY inventory_count_import_lock_ibfk_3;
ALTER TABLE INVENTORY_VAR_DCSN_RSN DROP FOREIGN KEY FPIVR_USER_LOGIN;
ALTER TABLE INVENTORY_VAR_DCSN_RSN DROP FOREIGN KEY inventory_var_dcsn_rsn_ibfk_6;
```

### hotwax-poorti
**Release tag:** v3.1.0    **Exact file:** upgrade/v3.1.0/UpgradeData.xml    **Type:** XML

```xml
<?xml version="1.0" encoding="UTF-8"?>
<entity-facade-xml type="ext-upgrade">
    <moqui.basic.Enumeration enumId="ADDRESS_VALIDATION" enumTypeId="PROD_STR_STNG" description="Validate order address on sales order create" enumName="Address Validation"/>
    <org.apache.ofbiz.product.store.ProductStoreSetting productStoreId="STORE" settingTypeEnumId="ADDRESS_VALIDATION" settingValue="N"/>

    <moqui.basic.StatusItem statusId="TASK_CREATED" statusTypeId="WORK_EFFORT_STATUS" statusCode="CREATED" sequenceNum="1" description="Created"/>

    <!-- POORTI_API, Admin_Print_PDF and ICC_API authorizations for the application user groups, moved here
         from component://oms/data/DH_ExtSeed_UserPermissionData.xml so they live with the artifact groups. -->
    <artifactGroups artifactGroupId="POORTI_API" description="Commerce POORTI API (via root resource)">
        <artifacts artifactTypeEnumId="AT_REST_PATH" inheritAuthz="Y" artifactName="/poorti"/>
        <authz artifactAuthzId="POORTI_API_ADMIN" userGroupId="ADMIN" authzTypeEnumId="AUTHZT_ALWAYS" authzActionEnumId="AUTHZA_ALL"/>
        <!-- Full permissions for the application user groups -->
        <authz artifactAuthzId="POORTI_API_SM" userGroupId="STORE_MANAGER" authzTypeEnumId="AUTHZT_ALWAYS" authzActionEnumId="AUTHZA_ALL"/>
        <authz artifactAuthzId="POORTI_API_WM" userGroupId="WAREHOUSE_MANAGER" authzTypeEnumId="AUTHZT_ALWAYS" authzActionEnumId="AUTHZA_ALL"/>
        <authz artifactAuthzId="POORTI_API_CSR" userGroupId="CSR" authzTypeEnumId="AUTHZT_ALWAYS" authzActionEnumId="AUTHZA_ALL"/>
        <authz artifactAuthzId="POORTI_API_OM" userGroupId="ORDER_MANAGER" authzTypeEnumId="AUTHZT_ALWAYS" authzActionEnumId="AUTHZA_ALL"/>
    </artifactGroups>

    <!-- Artifact data to allow Admin users to generate PDFs and other documents -->
    <artifactGroups artifactGroupId="Admin_Print_PDF" description="Admin App User">
        <artifacts artifactName="component://poorti/screen/pdf.xml" artifactTypeEnumId="AT_XML_SCREEN" inheritAuthz="Y"/>
    </artifactGroups>
    <moqui.security.ArtifactAuthz artifactAuthzId="Admin_PrintPdfScreen" userGroupId="ADMIN" artifactGroupId="Admin_Print_PDF"
                                  authzTypeEnumId="AUTHZT_ALWAYS" authzActionEnumId="AUTHZA_ALL"/>
    <moqui.security.ArtifactAuthz artifactAuthzId="Admin_PRINT_PDF_SM" userGroupId="STORE_MANAGER" artifactGroupId="Admin_Print_PDF"
                                  authzTypeEnumId="AUTHZT_ALWAYS" authzActionEnumId="AUTHZA_ALL"/>
    <moqui.security.ArtifactAuthz artifactAuthzId="Admin_PRINT_PDF_WM" userGroupId="WAREHOUSE_MANAGER" artifactGroupId="Admin_Print_PDF"
                                  authzTypeEnumId="AUTHZT_ALWAYS" authzActionEnumId="AUTHZA_ALL"/>
    <moqui.security.ArtifactAuthz artifactAuthzId="Admin_PRINT_PDF_CSR" userGroupId="CSR" artifactGroupId="Admin_Print_PDF"
                                  authzTypeEnumId="AUTHZT_ALWAYS" authzActionEnumId="AUTHZA_ALL"/>
    <moqui.security.ArtifactAuthz artifactAuthzId="Admin_PRINT_PDF_OM" userGroupId="ORDER_MANAGER" artifactGroupId="Admin_Print_PDF"
                                  authzTypeEnumId="AUTHZT_ALWAYS" authzActionEnumId="AUTHZA_ALL"/>
    <moqui.security.ArtifactAuthz artifactAuthzId="Admin_PRINT_PDF_MM" userGroupId="MERCHANDISE_MGR" artifactGroupId="Admin_Print_PDF"
                                  authzTypeEnumId="AUTHZT_ALWAYS" authzActionEnumId="AUTHZA_ALL"/>

    <artifactGroups artifactGroupId="ICC_API" description="Directed Inventory Cycle Count API (via root resource)">
        <artifacts artifactTypeEnumId="AT_REST_PATH" inheritAuthz="Y" artifactName="/inventory-cycle-count"/>
        <!-- Full permissions for the ADMIN user group -->
        <authz artifactAuthzId="ICC_API_ADMIN" userGroupId="ADMIN" authzTypeEnumId="AUTHZT_ALWAYS" authzActionEnumId="AUTHZA_ALL"/>
        <!-- Full permissions for the application user groups -->
        <authz artifactAuthzId="ICC_API_SM" userGroupId="STORE_MANAGER" authzTypeEnumId="AUTHZT_ALWAYS" authzActionEnumId="AUTHZA_ALL"/>
        <authz artifactAuthzId="ICC_API_WM" userGroupId="WAREHOUSE_MANAGER" authzTypeEnumId="AUTHZT_ALWAYS" authzActionEnumId="AUTHZA_ALL"/>
    </artifactGroups>
    <moqui.basic.EnumerationType enumTypeId="INVENTORY_RESET_TYPE" description="Inventory Reset Type"/>
    <moqui.basic.Enumeration enumId="INV_RESET_QOH" enumTypeId="INVENTORY_RESET_TYPE" description="Sets QOH to the provided inventory level, applying the same difference to ATP"/>
    <moqui.basic.Enumeration enumId="INV_RESET_ATP" enumTypeId="INVENTORY_RESET_TYPE" description="Sets ATP to the provided inventory level, applying the same difference to QOH"/>
    <moqui.basic.Enumeration enumId="INV_RESET_QOH_AND_ATP" enumTypeId="INVENTORY_RESET_TYPE" description="Receives only one inventory level (QOH), sets QOH according to it, and sets ATP by considering the reservations."/>
</entity-facade-xml>
```

### hotwax-poorti
**Release tag:** v3.1.0    **Exact file:** upgrade/v3.1.0/UpgradeSQL.sql    **Type:** SQL

```sql
-- Fix the TASK_CREATED StatusItem: some environments have it seeded with the wrong STATUS_TYPE_ID (WORKEFFORT_STATUS instead of the valid WORK_EFFORT_STATUS).
-- Update the row if it already exists
UPDATE STATUS_ITEM
SET STATUS_TYPE_ID = 'WORK_EFFORT_STATUS', STATUS_CODE = 'CREATED', SEQUENCE_NUM = 1, DESCRIPTION = 'Created'
WHERE STATUS_ID = 'TASK_CREATED';
```

### hotwax-poorti
**Release tag:** v3.1.1    **Exact file:** upgrade/v3.1.1/UpgradeData.xml    **Type:** XML

```xml
<?xml version="1.0" encoding="UTF-8"?>
<entity-facade-xml type="ext-upgrade">
</entity-facade-xml>
```

### hotwax-poorti
**Release tag:** v3.1.2    **Exact file:** upgrade/v3.1.2/UpgradeData.xml    **Type:** XML

```xml
<?xml version="1.0" encoding="UTF-8"?>
<entity-facade-xml type="ext-upgrade">
</entity-facade-xml>
```

### hotwax-poorti
**Release tag:** v3.1.3    **Exact file:** upgrade/v3.1.3/UpgradeData.xml    **Type:** XML

```xml
<?xml version="1.0" encoding="UTF-8"?>
<entity-facade-xml type="ext-upgrade">
</entity-facade-xml>
```

### hotwax-moqui-firebase
**Release tag:** v2.0.0-RC1    **Exact file:** upgrade/v2.0.0-RC1/UpgradeData.xml    **Type:** XML

```xml
<?xml version="1.0" encoding="UTF-8"?>
<entity-facade-xml type="ext-upgrade">
</entity-facade-xml>
```

### hotwax-moqui-firebase
**Release tag:** v2.1.0    **Exact file:** upgrade/v2.1.0/UpgradeData.xml    **Type:** XML

```xml
<?xml version="1.0" encoding="UTF-8"?>
<entity-facade-xml type="ext-upgrade">
    <!-- MOQUI_FIREBASE_API authorizations for the application user groups, moved here from
         component://oms/data/DH_ExtSeed_UserPermissionData.xml so they live with the artifact group. -->
    <artifactGroups artifactGroupId="MOQUI_FIREBASE_API" description="Moqui Firebase REST API (/firebase/*)">
        <artifacts artifactTypeEnumId="AT_REST_PATH" inheritAuthz="Y" artifactName="/firebase"/>
        <!-- Full permissions for ADMIN group users -->
        <authz artifactAuthzId="MOQUI_FIREBASE_API" userGroupId="ADMIN" authzTypeEnumId="AUTHZT_ALWAYS" authzActionEnumId="AUTHZA_ALL"/>
        <!-- Full permissions for the application user groups -->
        <authz artifactAuthzId="MOQUI_FIREBASE_API_SM" userGroupId="STORE_MANAGER" authzTypeEnumId="AUTHZT_ALWAYS" authzActionEnumId="AUTHZA_ALL"/>
        <authz artifactAuthzId="MOQUI_FIREBASE_API_WM" userGroupId="WAREHOUSE_MANAGER" authzTypeEnumId="AUTHZT_ALWAYS" authzActionEnumId="AUTHZA_ALL"/>
        <authz artifactAuthzId="MOQUI_FIREBASE_API_CSR" userGroupId="CSR" authzTypeEnumId="AUTHZT_ALWAYS" authzActionEnumId="AUTHZA_ALL"/>
        <authz artifactAuthzId="MOQUI_FIREBASE_API_OM" userGroupId="ORDER_MANAGER" authzTypeEnumId="AUTHZT_ALWAYS" authzActionEnumId="AUTHZA_ALL"/>
        <authz artifactAuthzId="MOQUI_FIREBASE_API_MM" userGroupId="MERCHANDISE_MGR" authzTypeEnumId="AUTHZT_ALWAYS" authzActionEnumId="AUTHZA_ALL"/>
    </artifactGroups>
</entity-facade-xml>
```

### rails
**Release tag:** v1.0.0-RC1    **Exact file:** upgrade/v1.0.0-RC1/UpgradeData.xml    **Type:** XML

```xml
<?xml version="1.0" encoding="UTF-8"?>
<entity-facade-xml type="ext-upgrade">
</entity-facade-xml>
```

### rails
**Release tag:** v1.1.0    **Exact file:** upgrade/v1.1.0/UpgradeData.xml    **Type:** XML

```xml
<?xml version="1.0" encoding="UTF-8"?>
<entity-facade-xml type="ext-upgrade">
    <!-- Mirrors data/EA_Ext_TypeMappingData.xml in full - NETSUITE_TAX_CODE/NETSUITE_PRICE_LEVEL's
         own Enumeration rows are deliberately NOT declared here (or in that file) - they're seeded
         by mantle-netsuite-connector (a shared dependency, loaded first), same as that file's own
         comments note. -->
    <org.apache.ofbiz.accounting.payment.PaymentMethodType paymentMethodTypeId="EXT_SHOP_CASH" description="EXT Cash"/>
    <org.apache.ofbiz.accounting.payment.PaymentMethodType paymentMethodTypeId="EXT_SHOP_AUTHZ_NET" description="authorize.net"/>

    <moqui.basic.Enumeration enumId="NETSUITE_DEFAULT_FACILITY" enumTypeId="NETSUITE" description="NetSuite Default Facility per Sales Channel"/>
    <moqui.basic.Enumeration enumId="NETSUITE_SHOPIFY_STORE" enumTypeId="NETSUITE" description="NetSuite Shopify Store record, per shopId"/>
    <moqui.basic.Enumeration enumId="NETSUITE_SLS_CHANNEL" enumTypeId="NETSUITE" description="NetSuite Sales Channel"/>
    <moqui.basic.Enumeration enumId="NETSUITE_DISC_MTHD" enumTypeId="NETSUITE" description="NetSuite Discount Method"/>
    <moqui.basic.Enumeration enumId="NETSUITE_SHP_ITEM" enumTypeId="NETSUITE" description="NetSuite Shipping Charge Item"/>
    <moqui.basic.Enumeration enumId="NETSUITE_SO_CUSTOM_FORM" enumTypeId="NETSUITE" description="NetSuite Sales Order Custom Form"/>
    <moqui.basic.Enumeration enumId="NETSUITE_SO_ORDER_TYPE" enumTypeId="NETSUITE" description="NetSuite Sales Order Type custom segment"/>
    <moqui.basic.Enumeration enumId="NETSUITE_SO_CREDIT_STATUS" enumTypeId="NETSUITE" description="NetSuite Sales Order Credit Status custom segment"/>

    <co.hotwax.integration.IntegrationTypeMapping integrationMappingId="NETSUITE_DEFAULT_FACILITY_WEB"
        integrationTypeId="NETSUITE_DEFAULT_FACILITY" mappingKey="WEB_SALES_CHANNEL" mappingValue="4"
        description="Default facility for Web channel orders - NetSuite Internal ID"/>
    <co.hotwax.integration.IntegrationTypeMapping integrationMappingId="NETSUITE_SLS_CHANNEL_WEB"
        integrationTypeId="NETSUITE_SLS_CHANNEL" mappingKey="WEB_SALES_CHANNEL" mappingValue="1"
        description="Ecommerce - confirmed from real GET response"/>
    <co.hotwax.integration.IntegrationTypeMapping integrationMappingId="NETSUITE_SLS_CHANNEL_POS"
        integrationTypeId="NETSUITE_SLS_CHANNEL" mappingKey="POS_SALES_CHANNEL" mappingValue="2"
        description="Retail (label unconfirmed) - id 2 per sheet's POS sample value"/>
    <co.hotwax.integration.IntegrationTypeMapping integrationMappingId="NETSUITE_SHOPIFY_STORE"
        integrationTypeId="NETSUITE_SHOPIFY_STORE" mappingKey="1671180" mappingValue="1"
        description="Rails - rails-25.myshopify.com"/>
    <co.hotwax.integration.IntegrationTypeMapping integrationMappingId="NETSUITE_DISC_MTHD_SHOPIFY_ITEM_DISC"
        integrationTypeId="NETSUITE_DISC_MTHD" mappingKey="SHOPIFY_ITEM_DISC" mappingValue="54214"
        description="Shopify Item Discount"/>
    <co.hotwax.integration.IntegrationTypeMapping integrationMappingId="NETSUITE_SHP_ITEM_SHOPIFY_SHIPPING"
        integrationTypeId="NETSUITE_SHP_ITEM" mappingKey="SHOPIFY_SHIPPING" mappingValue="54213"
        description="Shopify Shipping"/>
    <co.hotwax.integration.IntegrationTypeMapping integrationMappingId="NETSUITE_SHP_ITEM_SHOPIFY_TAX_VARIANCE"
        integrationTypeId="NETSUITE_SHP_ITEM" mappingKey="SHOPIFY_TAX_VARIANCE" mappingValue="109068"
        description="Shopify Tax Variance"/>
    <co.hotwax.integration.IntegrationTypeMapping integrationMappingId="NETSUITE_SHP_ITEM_CO_DELIVERY_FEE"
        integrationTypeId="NETSUITE_SHP_ITEM" mappingKey="RETAIL DELIVERY FEE - COLORADO" mappingValue="136457"
        description="Shopify Special Regional Tax - Colorado Retail Delivery Fee"/>
    <co.hotwax.integration.IntegrationTypeMapping integrationMappingId="NETSUITE_SHP_ITEM_MN_DELIVERY_FEE"
        integrationTypeId="NETSUITE_SHP_ITEM" mappingKey="ROAD IMPROVEMENT AND FOOD DELIVERY FEE - MINNESOTA" mappingValue="136457"
        description="Shopify Special Regional Tax - Minnesota Road Improvement and Food Delivery Fee"/>
    <co.hotwax.integration.IntegrationTypeMapping integrationMappingId="NETSUITE_DISC_MTHD_SHIPPING_DISC"
        integrationTypeId="NETSUITE_DISC_MTHD" mappingKey="SHOPIFY_SHIPPING_DISC" mappingValue="109066"
        description="Shopify Shipping Discount"/>
    <co.hotwax.integration.IntegrationTypeMapping integrationMappingId="NETSUITE_TAX_CODE_withTaxId"
        integrationTypeId="NETSUITE_TAX_CODE" mappingKey="withTaxId" mappingValue="Taxable"
        description="NetSuite tax code refName for shipping with tax"/>
    <co.hotwax.integration.IntegrationTypeMapping integrationMappingId="NETSUITE_TAX_CODE_withoutTaxId"
        integrationTypeId="NETSUITE_TAX_CODE" mappingKey="withoutTaxId" mappingValue="-Not Taxable-"
        description="NetSuite tax code refName for shipping without tax"/>
    <co.hotwax.integration.IntegrationTypeMapping integrationMappingId="NETSUITE_PRICE_LEVEL"
        integrationTypeId="NETSUITE_PRICE_LEVEL" mappingKey="PRICE_LEVEL" mappingValue="-1"
        description="Rails price level - client sample value, not separately confirmed"/>
    <co.hotwax.integration.IntegrationTypeMapping integrationMappingId="NETSUITE_SO_CUSTOM_FORM_DEFAULT"
        integrationTypeId="NETSUITE_SO_CUSTOM_FORM" mappingKey="DEFAULT" mappingValue="257"
        description="Rails Sales Order custom form - confirmed with client"/>
    <co.hotwax.integration.IntegrationTypeMapping integrationMappingId="NETSUITE_SO_ORDER_TYPE_DEFAULT"
        integrationTypeId="NETSUITE_SO_ORDER_TYPE" mappingKey="DEFAULT" mappingValue="10"
        description="Rails custbody_rails_order_type value - confirmed with client"/>
    <co.hotwax.integration.IntegrationTypeMapping integrationMappingId="NETSUITE_SO_CREDIT_STATUS_DEFAULT"
        integrationTypeId="NETSUITE_SO_CREDIT_STATUS" mappingKey="DEFAULT" mappingValue="3"
        description="Rails custbody_r_credit_status value - confirmed with client"/>

<moqui.service.message.SystemMessageRemote systemMessageRemoteId="ALC_RAILS"
        description="Artifact Life Cycle API configuration for Rails NetSuite return sync error logging"
        sendUrl="https://alc-dev.hotwax.io/rest/s1/artifact-life-cycle"
        internalId="Rails"
        username="rails.user"
        password=""/>

    <moqui.service.message.SystemMessageType systemMessageTypeId="AlcNetSuiteReturnSyncError"
        description="Log NetSuite return sync transaction errors to ALC"
        sendServiceName="co.hotwax.rails.netsuite.return.ReturnSyncServices.send#NetSuiteReturnSyncErrors"/>

    <moqui.service.message.SystemMessageTypeParameter systemMessageTypeId="AlcNetSuiteReturnSyncError"
        parameterName="sendSmrId"
        parameterValue="ALC_RAILS"
        systemMessageRemoteId=""/>

    <moqui.basic.Enumeration enumId="ECOM_RTN_CHANNEL"
        enumTypeId="RETURN_CHANNEL"
        enumCode="ECOM_RTN_CHANNEL"
        enumName="Shopify Admin"
        description="Shopify Admin"/>
    <moqui.basic.Enumeration enumId="POS_RTN_CHANNEL"
        enumTypeId="RETURN_CHANNEL"
        enumCode="POS_RTN_CHANNEL"
        enumName="Shopify POS"
        description="Shopify POS"/>

    <moqui.basic.Enumeration enumId="NETSUITE_PMT_MTHD" enumTypeId="NETSUITE" description="NetSuite payment method"/>
    <moqui.basic.Enumeration enumId="NETSUITE_GIFT_CARD" enumTypeId="NETSUITE" description="NetSuite gift card"/>
    <moqui.basic.Enumeration enumId="NETSUITE_ITEM_ID" enumTypeId="NETSUITE" description="NetSuite item mapping"/>
    <moqui.basic.Enumeration enumId="NETSUITE_RESTLET_URL" enumTypeId="NETSUITE" enumCode="NETSUITE_RESTLET_URL" enumName="NetSuite Restlet URL Mapping" description="Mapping keys for NetSuite restlet script URL paths"/>
    <moqui.basic.Enumeration enumId="NETSUITE_RETURN_TAX_CODE" enumTypeId="NETSUITE" enumCode="NETSUITE_RETURN_TAX_CODE" enumName="NetSuite Return Tax Code Mapping" description="Mapping keys for NetSuite return tax codes"/>
    <moqui.basic.Enumeration enumId="NETSUITE_RETURN_URL" enumTypeId="NETSUITE" enumCode="NETSUITE_RETURN_URL" enumName="NetSuite Return Record URL Mapping" description="Mapping keys for NetSuite return record URLs"/>
    <moqui.basic.Enumeration enumId="NETSUITE_RTN_CONFIG" enumTypeId="NETSUITE" enumCode="NETSUITE_RTN_CONFIG" enumName="NetSuite Return Configuration Mapping" description="Mapping keys for NetSuite return configuration"/>

    <co.hotwax.integration.IntegrationTypeMapping integrationMappingId="NS_GIFT_CARD_ITEM" integrationTypeId="NETSUITE_GIFT_CARD" mappingKey="GIFT_CARD" mappingValue="109067" description="Gift card and Shopify Store Credit item mapping"/>
    <co.hotwax.integration.IntegrationTypeMapping integrationMappingId="NS_ITEM_APPEASEMENT_NO_RES" integrationTypeId="NETSUITE_ITEM_ID" mappingKey="appeasementNoResLineItem" mappingValue="146406" description="NetSuite appeasement RMA line item id"/>

    <co.hotwax.integration.IntegrationTypeMapping integrationMappingId="NS_RESTLET_CREATE_CM_REFUND" integrationTypeId="NETSUITE_RESTLET_URL" mappingKey="createCreditMemoRefund" mappingValue="?script=4712&amp;deploy=1" description="Restlet URL for credit memo and customer refund creation"/>
    <co.hotwax.integration.IntegrationTypeMapping integrationMappingId="NS_RESTLET_GET_ITEM_RECEIPTS" integrationTypeId="NETSUITE_RESTLET_URL" mappingKey="getItemReceipts" mappingValue="?script=4713&amp;deploy=1" description="Restlet URL for fetching item receipts"/>

    <co.hotwax.integration.IntegrationTypeMapping integrationMappingId="NS_RETURN_URL_RMA" integrationTypeId="NETSUITE_RETURN_URL" mappingKey="RMA" mappingValue="" description="NetSuite return authorization URL prefix"/>
    <co.hotwax.integration.IntegrationTypeMapping integrationMappingId="NS_RETURN_URL_IR" integrationTypeId="NETSUITE_RETURN_URL" mappingKey="IR" mappingValue="" description="NetSuite item receipt URL prefix"/>
    <co.hotwax.integration.IntegrationTypeMapping integrationMappingId="NS_RETURN_URL_CM" integrationTypeId="NETSUITE_RETURN_URL" mappingKey="CM" mappingValue="" description="NetSuite credit memo URL prefix"/>

    <co.hotwax.integration.IntegrationTypeMapping integrationMappingId="NS_RETURN_TAX_WITH" integrationTypeId="NETSUITE_RETURN_TAX_CODE" mappingKey="withTaxId" mappingValue="10" description="NetSuite return tax code for items with tax"/>
    <co.hotwax.integration.IntegrationTypeMapping integrationMappingId="NS_RETURN_TAX_WITHOUT" integrationTypeId="NETSUITE_RETURN_TAX_CODE" mappingKey="withoutTaxId" mappingValue="-7" description="NetSuite return tax code for items without tax"/>


    <co.hotwax.integration.IntegrationTypeMapping integrationMappingId="NS_RTN_DEFAULT_RESTOCK_LOC" integrationTypeId="NETSUITE_RTN_CONFIG" mappingKey="DefaultRestockLocationId" mappingValue="4" description="Default fallback NetSuite restock location"/>
    <co.hotwax.integration.IntegrationTypeMapping integrationMappingId="NS_RTN_RMA_REC_BIN" integrationTypeId="NETSUITE_RTN_CONFIG" mappingKey="RmaRecBinId" mappingValue="" description="NetSuite RMA receive bin id for warehouse item receipts"/>

    <moqui.basic.Enumeration enumId="NS_RTN_FEED_SYNC" enumTypeId="PROD_STR_STNG" description="Enable NetSuite return sync from data feed" enumName="Enable NetSuite Return Feed"/>
    <moqui.basic.Enumeration enumId="NS_RTN_SYNC_START_DATE" enumTypeId="PROD_STR_STNG" description="NetSuite return sync start date" enumName="NetSuite Return Sync Start Date"/>

    <org.apache.ofbiz.product.store.ProductStoreSetting productStoreId="STORE" settingTypeEnumId="NS_RTN_FEED_SYNC" settingValue="false"/>
    <org.apache.ofbiz.product.store.ProductStoreSetting productStoreId="STORE" settingTypeEnumId="NS_RTN_SYNC_START_DATE" settingValue=""/>

    <moqui.entity.document.DataDocument dataDocumentId="NetSuiteReturnHeaderEvent"
        documentName="Rails NetSuite Return Header Event"
        primaryEntityName="org.apache.ofbiz.order.return.ReturnHeader"
        documentTitle="${returnId}">
        <fields fieldSeqId="01" fieldPath="returnId" defaultDisplay="N"/>
        <fields fieldSeqId="02" fieldPath="statusId"/>
        <fields fieldSeqId="03" fieldPath="returnHeaderTypeId"/>
        <fields fieldSeqId="04" fieldPath="returnChannelEnumId"/>
        <fields fieldSeqId="05" fieldPath="entryDate"/>
        <fields fieldSeqId="06" fieldPath="fromPartyId"/>
        <conditions conditionSeqId="01" fieldNameAlias="returnChannelEnumId" operator="not-equals" fieldValue="LOOP_RETURN_CHANNEL"/>
    </moqui.entity.document.DataDocument>

    <moqui.entity.document.DataDocument dataDocumentId="NetSuiteShipmentReceiptEvent"
        documentName="Rails NetSuite Shipment Receipt Event"
        primaryEntityName="org.apache.ofbiz.shipment.receipt.ShipmentReceipt"
        documentTitle="${receiptId}">
        <fields fieldSeqId="01" fieldPath="receiptId" defaultDisplay="N"/>
        <fields fieldSeqId="02" fieldPath="returnId"/>
        <fields fieldSeqId="03" fieldPath="returnItemSeqId"/>
        <fields fieldSeqId="04" fieldPath="quantityAccepted"/>
        <fields fieldSeqId="05" fieldPath="datetimeReceived"/>
        <fields fieldSeqId="06" fieldPath="org.apache.ofbiz.order.return.ReturnItem:org.apache.ofbiz.order.return.ReturnHeader:returnChannelEnumId"/>
        <conditions conditionSeqId="01" fieldNameAlias="returnId" operator="is-not-null"/>
        <conditions conditionSeqId="02" fieldNameAlias="returnChannelEnumId" operator="not-equals" fieldValue="LOOP_RETURN_CHANNEL"/>
    </moqui.entity.document.DataDocument>

    <moqui.entity.document.DataDocument dataDocumentId="NetSuiteReturnItemResponseEvent"
        documentName="Rails NetSuite Return Item Response Event"
        primaryEntityName="org.apache.ofbiz.order.return.ReturnItemResponse"
        documentTitle="${returnItemResponseId}">
        <fields fieldSeqId="01" fieldPath="returnItemResponseId" defaultDisplay="N"/>
        <fields fieldSeqId="04" fieldPath="orderPaymentPreferenceId"/>
        <fields fieldSeqId="05" fieldPath="responseDate"/>
        <fields fieldSeqId="06" fieldPath="orderPaymentPreference:paymentMethodTypeId"/>
        <fields fieldSeqId="07" fieldPath="org.apache.ofbiz.order.return.ReturnHeader:returnChannelEnumId"/>
        <conditions conditionSeqId="01" fieldNameAlias="returnId" operator="is-not-null"/>
        <conditions conditionSeqId="02" fieldNameAlias="returnChannelEnumId" operator="not-equals" fieldValue="LOOP_RETURN_CHANNEL"/>
    </moqui.entity.document.DataDocument>

    <moqui.entity.document.DataDocument dataDocumentId="NetSuiteReturnHeaderHistoryEvent"
        documentName="Rails NetSuite Return Header History Event"
        primaryEntityName="co.netsuite.integration.NetSuiteReturnHeaderHistory"
        documentTitle="${netSuiteReturnHeaderHistoryId}">
        <fields fieldSeqId="01" fieldPath="netSuiteReturnHeaderHistoryId" defaultDisplay="N"/>
        <fields fieldSeqId="03" fieldPath="rmaId"/>
        <fields fieldSeqId="04" fieldPath="inventoryReceiptId"/>
        <fields fieldSeqId="05" fieldPath="syncStatus"/>
        <conditions conditionSeqId="02" fieldNameAlias="inventoryReceiptId" operator="is-not-null"/>
    </moqui.entity.document.DataDocument>

    <moqui.entity.document.DataDocument dataDocumentId="NetSuiteReturnCreditMemoReadyEvent"
        documentName="Rails NetSuite Return Credit Memo Ready Event"
        primaryEntityName="co.netsuite.integration.NetSuiteReturnHeaderHistory"
        documentTitle="${netSuiteReturnHeaderHistoryId}">
        <fields fieldSeqId="01" fieldPath="netSuiteReturnHeaderHistoryId" defaultDisplay="N"/>
        <fields fieldSeqId="02" fieldPath="returnId"/>
        <fields fieldSeqId="03" fieldPath="creditMemoId"/>
        <fields fieldSeqId="04" fieldPath="syncStatus"/>
        <conditions conditionSeqId="01" fieldNameAlias="returnId" operator="is-not-null"/>
        <conditions conditionSeqId="02" fieldNameAlias="creditMemoId" operator="is-not-null"/>
    </moqui.entity.document.DataDocument>

    <moqui.entity.feed.DataFeed dataFeedId="NetSuiteReturnsFeed"
        dataFeedTypeEnumId="DTFDTP_RT_PUSH"
        feedName="Rails NetSuite Return Lifecycle Feed"
        feedReceiveServiceName="co.hotwax.rails.netsuite.return.ReturnSyncServices.receive#ReturnEventsFeed">
        <documents dataDocumentId="NetSuiteReturnHeaderEvent"/>
        <documents dataDocumentId="NetSuiteShipmentReceiptEvent"/>
        <documents dataDocumentId="NetSuiteReturnItemResponseEvent"/>
        <documents dataDocumentId="NetSuiteReturnHeaderHistoryEvent"/>
        <documents dataDocumentId="NetSuiteReturnCreditMemoReadyEvent"/>
    </moqui.entity.feed.DataFeed>

    <moqui.service.job.ServiceJob jobName="sync_NetSuiteItemReceipts"
        description="Sync NetSuite Item Receipts with OMS return history"
        serviceName="co.hotwax.rails.netsuite.return.ReturnSyncServices.sync#NetSuiteItemReceipts"
        cronExpression="0 */15 * ? * *"
        paused="Y"
        expireLockTime="30">
        <parameters parameterName="fromDate"/>
        <parameters parameterName="thruDate"/>
        <parameters parameterName="fromDatetime"/>
        <parameters parameterName="toDatetime"/>
        <parameters parameterName="limit" parameterValue="1000"/>
        <parameters parameterName="offset" parameterValue="0"/>
        <parameters parameterName="jobName" parameterValue="sync_NetSuiteItemReceipts"/>
        <parameters parameterName="skipLastRunTimeUpdate" parameterValue="false"/>
        <parameters parameterName="lastRunTime"/>
    </moqui.service.job.ServiceJob>

    <moqui.service.job.ServiceJob jobName="sync_NetSuiteReturnTransactions"
        description="Fallback sync for eligible returns via NetSuite return transactions service"
        serviceName="co.hotwax.rails.netsuite.return.ReturnSyncServices.sync#EligibleNetSuiteReturnTransactions"
        cronExpression="0 */30 * ? * *"
        paused="Y"
        expireLockTime="60">
        <parameters parameterName="action" parameterValue="AUTO"/>
        <parameters parameterName="returnId" parameterValue=""/>
    </moqui.service.job.ServiceJob>

    <moqui.entity.document.DataDocument dataDocumentId="NetSuiteReturnCreditMemoReadyEvent"
        documentName="Rails NetSuite Return Credit Memo Ready Event"
        primaryEntityName="co.netsuite.integration.NetSuiteReturnHeaderHistory"
        documentTitle="${netSuiteReturnHeaderHistoryId}">
        <fields fieldSeqId="03" fieldPath="creditMemoId"/>
        <fields fieldSeqId="04" fieldPath="syncStatus"/>
        <conditions conditionSeqId="02" fieldNameAlias="creditMemoId" operator="is-not-null"/>
    </moqui.entity.document.DataDocument>

    <moqui.service.job.ServiceJob jobName="sync_NetSuiteExchangeOrderCreditMemoReferences"
        description="Fallback sync for eligible exchange orders missing NetSuite credit memo references"
        serviceName="co.hotwax.rails.netsuite.return.ReturnSyncServices.sync#EligibleExchangeOrderCreditMemoReferences"
        cronExpression="0 */30 * ? * *"
        paused="Y"
        expireLockTime="60">
        <parameters parameterName="fromDate"/>
        <parameters parameterName="thruDate"/>
        <parameters parameterName="orderIds"/>
        <parameters parameterName="limit" parameterValue="1000"/>
        <parameters parameterName="offset" parameterValue="0"/>
    </moqui.service.job.ServiceJob>


</entity-facade-xml>
```

### rails
**Release tag:** v1.1.1    **Exact file:** upgrade/v1.1.1/UpgradeData.xml    **Type:** XML

```xml
<?xml version="1.0" encoding="UTF-8"?>
<entity-facade-xml type="ext-upgrade">
    <!-- Seed data with correct enum names to map return channels -->
    <moqui.basic.Enumeration enumId="ADMIN_RTN_CHANNEL" enumTypeId="RETURN_CHANNEL" enumCode="ADMIN_RTN_CHANNEL" enumName="Shopify Web" description="Admin Return Channel"/>
    <moqui.basic.Enumeration enumId="POS_RTN_CHANNEL" enumTypeId="RETURN_CHANNEL" enumCode="POS_RTN_CHANNEL" enumName="Point of Sale" description="Shopify POS"/>
    <moqui.basic.Enumeration enumId="LOOP_RETURN_CHANNEL" enumTypeId="RETURN_CHANNEL" enumCode="LOOP_RETURN_CHANNEL" enumName="Loop Returns &amp; Exchanges" description="Loop Return Channel"/>

    <org.apache.ofbiz.accounting.payment.PaymentMethodType paymentMethodTypeId="EXT_POS_PAX_TERMINAL" description="External PAX Terminal"/>
</entity-facade-xml>
```

### rails
**Release tag:** v1.1.2    **Exact file:** upgrade/v1.1.2/UpgradeData.xml    **Type:** XML

```xml
<?xml version="1.0" encoding="UTF-8"?>
<entity-facade-xml type="ext-upgrade">
</entity-facade-xml>
```

### rails
**Release tag:** v1.1.3    **Exact file:** upgrade/v1.1.3/UpgradeData.xml    **Type:** XML

```xml
<?xml version="1.0" encoding="UTF-8"?>
<entity-facade-xml type="ext-upgrade">
    <moqui.entity.document.DataDocument dataDocumentId="NetSuiteShipmentReceiptEvent">
        <fields fieldSeqId="07" fieldPath="org.apache.ofbiz.order.return.ReturnItem:org.apache.ofbiz.order.return.ReturnHeader:statusId"/>
        <conditions conditionSeqId="03" fieldNameAlias="statusId" fieldValue="RETURN_COMPLETED"/>
    </moqui.entity.document.DataDocument>

    <moqui.entity.document.DataDocument dataDocumentId="NetSuiteReturnItemResponseEvent">
        <fields fieldSeqId="08" fieldPath="org.apache.ofbiz.order.return.ReturnHeader:statusId"/>
        <conditions conditionSeqId="03" fieldNameAlias="statusId" fieldValue="RETURN_COMPLETED"/>
    </moqui.entity.document.DataDocument>

    <org.apache.ofbiz.common.property.SystemProperty systemResourceId="hotwax.netsuite" systemPropertyValue="2026-08-16 20:59:55" systemPropertyId="netsuite_return_sync_from_date"/>
    <org.apache.ofbiz.common.property.SystemProperty systemResourceId="hotwax.netsuite" systemPropertyId="go.live.launch.date" systemPropertyValue="2026-08-16 20:59:55"/>
</entity-facade-xml>
```

### rails
**Release tag:** v1.1.4    **Exact file:** upgrade/v1.1.4/UpgradeData.xml    **Type:** XML

```xml
<?xml version="1.0" encoding="UTF-8"?>
<entity-facade-xml type="ext-upgrade">
</entity-facade-xml>
```

### rails
**Release tag:** v1.1.5    **Exact file:** upgrade/v1.1.5/UpgradeData.xml    **Type:** XML

```xml
<?xml version="1.0" encoding="UTF-8"?>
<entity-facade-xml type="ext-upgrade">
</entity-facade-xml>
```

### gorjana-maarg
**Release tag:** v3.0.0-RC1    **Exact file:** upgrade/v3.0.0-RC1/UpgradeData.xml    **Type:** XML

```xml
<?xml version="1.0" encoding="UTF-8"?>
<entity-facade-xml type="ext-upgrade">
    <org.apache.ofbiz.common.property.SystemProperty systemResourceId="hotwax.netsuite" systemPropertyId="go.live.launch.date" systemPropertyValue="2024-10-06 00:00:00"/>

    <moqui.entity.document.DataDocument dataDocumentId="NetSuiteAfterShipCompletedReturnEvent"
        documentName="Gorjana NetSuite AfterShip Completed Return Header Event"
        primaryEntityName="org.apache.ofbiz.order.return.ReturnHeader"
        documentTitle="${returnId}">
        <fields fieldSeqId="01" fieldPath="returnId" defaultDisplay="N"/>
        <fields fieldSeqId="02" fieldPath="statusId"/>
        <fields fieldSeqId="03" fieldPath="returnChannelEnumId"/>
        <fields fieldSeqId="04" fieldPath="destinationFacilityId"/>
        <fields fieldSeqId="05" fieldPath="co.netsuite.integration.NetSuiteReturnHeaderHistory:netSuiteReturnHeaderHistoryId"/>
        <fields fieldSeqId="06" fieldPath="co.netsuite.integration.NetSuiteReturnHeaderHistory:rmaId"/>
        <conditions conditionSeqId="01" fieldNameAlias="returnChannelEnumId" operator="equals" fieldValue="AFTSHIP_RTN_CHANNEL"/>
        <conditions conditionSeqId="02" fieldNameAlias="statusId" operator="equals" fieldValue="RETURN_COMPLETED"/>
        <conditions conditionSeqId="03" fieldNameAlias="destinationFacilityId" operator="is-not-null"/>
        <conditions conditionSeqId="04" fieldNameAlias="destinationFacilityId" operator="not-equals" fieldValue="_NA_"/>
        <conditions conditionSeqId="05" fieldNameAlias="netSuiteReturnHeaderHistoryId" operator="is-not-null"/>
        <conditions conditionSeqId="06" fieldNameAlias="rmaId" operator="is-not-null"/>
    </moqui.entity.document.DataDocument>

    <moqui.basic.Enumeration enumId="AFTSHP_SCE_WTY" enumTypeId="RETURN_CHANNEL" enumCode="AFTSHP_SCE_WTY" enumName="AfterShip Store Credit Exception Warranty" description="Store Credit Exception Request" relatedEnumId="AFTSHIP_SALES_CNL"/>
    <co.hotwax.integration.IntegrationTypeMapping integrationMappingId="AFTWPGCHNL_SCE_NM" integrationTypeId="AFTSHP_WTY_PAGE_CHNL" mappingKey="Store Credit Exception Request" mappingValue="AFTSHP_SCE_WTY" description="Store Credit Exception Request page name -> AfterShip store credit exception warranty channel"/>

    <co.hotwax.integration.IntegrationTypeMapping integrationMappingId="NS_DMG_CODE_003_TXT"
            integrationTypeId="NETSUITE_DMGD_LOC"
            mappingKey="003 Plating"
            mappingValue="RTN_DMG_PLT"
            description="AfterShip warranty reason 003 Plating -> RTN_DMG_PLT"/>
    <co.hotwax.integration.IntegrationTypeMapping integrationMappingId="NS_DMG_CODE_004_TXT"
            integrationTypeId="NETSUITE_DMGD_LOC"
            mappingKey="004 Closure"
            mappingValue="RTN_DMG_CLS"
            description="AfterShip warranty reason 004 Closure -> RTN_DMG_CLS"/>
    <co.hotwax.integration.IntegrationTypeMapping integrationMappingId="NS_DMG_CODE_005_TXT"
            integrationTypeId="NETSUITE_DMGD_LOC"
            mappingKey="005 Chain"
            mappingValue="RTN_DMG_CHN"
            description="AfterShip warranty reason 005 Chain -> RTN_DMG_CHN"/>
    <co.hotwax.integration.IntegrationTypeMapping integrationMappingId="NS_DMG_CODE_006_TXT"
            integrationTypeId="NETSUITE_DMGD_LOC"
            mappingKey="006 Shape"
            mappingValue="RTN_DMG_SHP"
            description="AfterShip warranty reason 006 Shape -> RTN_DMG_SHP"/>
    <co.hotwax.integration.IntegrationTypeMapping integrationMappingId="NS_DMG_CODE_007_TXT"
            integrationTypeId="NETSUITE_DMGD_LOC"
            mappingKey="007 Missing Comp"
            mappingValue="RTN_DMG_MIS"
            description="AfterShip warranty reason 007 Missing Comp -> RTN_DMG_MIS"/>
    <co.hotwax.integration.IntegrationTypeMapping integrationMappingId="NS_DMG_NOTE_STYLE"
            integrationTypeId="NETSUITE_DMGD_LOC"
            mappingKey="Style is damaged"
            mappingValue="22"
            description="AfterShip warranty generic damaged reason -> primary damaged location 22"/>
</entity-facade-xml>
```

### gorjana-maarg
**Release tag:** v3.0.0-RC1    **Exact file:** upgrade/v3.0.0-RC1/UpgradeSQL.sql    **Type:** SQL

```sql
ALTER TABLE adp_worker_history DROP COLUMN netsuite_customer_id;
ALTER TABLE adp_worker_history DROP COLUMN netsuite_invoice_id;
```

### gorjana-maarg
**Release tag:** v3.0.5    **Exact file:** upgrade/v3.0.5/UpgradeData.xml    **Type:** XML

```xml
<?xml version="1.0" encoding="UTF-8"?>
<entity-facade-xml type="ext-upgrade">
    <!-- ============================================================
         WorkEffort Enumerations
         ============================================================ -->
    <moqui.basic.Enumeration enumId="RETURN_HOLD" enumTypeId="WorkEffortType" description="Return Hold"/>
    <moqui.basic.Enumeration enumId="NO_POP_WARRANTY_HOLD" enumTypeId="WorkEffortPurposeType" description="No Proof of Purchase Warranty Hold"/>

    <moqui.basic.Enumeration enumId="NS_AFTSHIP_RTN_WH_IR" enumTypeId="PROD_STR_STNG" description="Create NetSuite Item Receipt automatically for completed AfterShip warehouse returns" enumName="AfterShip Warehouse Return IR"/>
    <org.apache.ofbiz.product.store.ProductStoreSetting productStoreId="STORE" settingTypeEnumId="NS_AFTSHIP_RTN_WH_IR" settingValue="N"/>

    <!-- Add 'Fixture Damages' variance reason and map to NetSuite variance group -->
    <moqui.basic.Enumeration enumId="VAR_FIXTURE_DAMAGES" enumTypeId="IID_REASON" description="Fixture Damages" enumCode="VAR_FIXTURE_DAMAGES"/>
    <co.hotwax.common.enum.EnumerationGroupMember enumerationId="VAR_FIXTURE_DAMAGES" enumerationGroupId="IA_VAR_NETSUITE"/>
</entity-facade-xml>
```

### gorjana-maarg
**Release tag:** v3.0.5    **Exact file:** upgrade/v3.0.5/UpgradeSQL.sql    **Type:** SQL

```sql
DELETE FROM product_store_email_setting
WHERE product_store_id = 'STORE'
  AND email_type = 'PRDS_ODR_SHIP_SHIPP';
```

### gorjana-maarg
**Release tag:** v3.1.0    **Exact file:** upgrade/v3.1.0/UpgradeData.xml    **Type:** XML

```xml
<?xml version="1.0" encoding="UTF-8"?>
<entity-facade-xml type="ext-upgrade">
    <!-- ============================================================
         WorkEffort Enumerations
         ============================================================ -->
    <moqui.basic.Enumeration enumId="RETURN_HOLD" enumTypeId="WorkEffortType" description="Return Hold"/>
    <moqui.basic.Enumeration enumId="NO_POP_WARRANTY_HOLD" enumTypeId="WorkEffortPurposeType" description="No Proof of Purchase Warranty Hold"/>

    <moqui.basic.Enumeration enumId="NS_AFTSHIP_RTN_WH_IR" enumTypeId="PROD_STR_STNG" description="Create NetSuite Item Receipt automatically for completed AfterShip warehouse returns" enumName="AfterShip Warehouse Return IR"/>
    <org.apache.ofbiz.product.store.ProductStoreSetting productStoreId="STORE" settingTypeEnumId="NS_AFTSHIP_RTN_WH_IR" settingValue="N"/>
</entity-facade-xml>
```

### gorjana-maarg
**Release tag:** v3.1.2    **Exact file:** upgrade/v3.1.2/UpgradeData.xml    **Type:** XML

```xml
<?xml version="1.0" encoding="UTF-8"?>
<entity-facade-xml type="ext-upgrade">
</entity-facade-xml>
```

### adoc-maarg
**Release tag:** v2.0.0-RC1    **Exact file:** upgrade/v2.0.0-RC1/UpgradeData.xml    **Type:** XML

```xml
<?xml version="1.0" encoding="UTF-8"?>
<entity-facade-xml type="ext-upgrade">
</entity-facade-xml>
```

### adoc-maarg
**Release tag:** v2.1.0    **Exact file:** upgrade/v2.1.0/UpgradeData.xml    **Type:** XML

```xml
<?xml version="1.0" encoding="UTF-8"?>
<entity-facade-xml type="ext-upgrade">
</entity-facade-xml>
```

### adoc-maarg
**Release tag:** v2.1.1    **Exact file:** upgrade/v2.1.1/UpgradeData.xml    **Type:** XML

```xml
<?xml version="1.0" encoding="UTF-8"?>
<entity-facade-xml type="ext-upgrade">
</entity-facade-xml>
```

### oms-bi
**Release tag:** v2.0.0-RC1    **Exact file:** upgrade/v2.0.0-RC1/UpgradeData.xml    **Type:** XML

```xml
<?xml version="1.0" encoding="UTF-8"?>
<entity-facade-xml type="ext-upgrade">
</entity-facade-xml>
```

### oms-bi
**Release tag:** v2.1.0    **Exact file:** upgrade/v2.1.0/UpgradeData.xml    **Type:** XML

```xml
<?xml version="1.0" encoding="UTF-8"?>
<entity-facade-xml type="ext-upgrade">
</entity-facade-xml>
```

### hotwax-predictspring
**Release tag:** v2.0.0-RC1    **Exact file:** upgrade/v2.0.0-RC1/UpgradeData.xml    **Type:** XML

```xml
<?xml version="1.0" encoding="UTF-8"?>
<entity-facade-xml type="ext-upgrade">
</entity-facade-xml>
```

### hotwax-predictspring
**Release tag:** v2.1.0    **Exact file:** upgrade/v2.1.0/UpgradeData.xml    **Type:** XML

```xml
<?xml version="1.0" encoding="UTF-8"?>
<entity-facade-xml type="ext-upgrade">
</entity-facade-xml>
```

### hotwax-gorgias
**Release tag:** v2.0.0-RC1    **Exact file:** upgrade/v2.0.0-RC1/UpgradeData.xml    **Type:** XML

```xml
<?xml version="1.0" encoding="UTF-8"?>
<entity-facade-xml type="ext-upgrade">
</entity-facade-xml>
```

### hotwax-gorgias
**Release tag:** v2.1.0    **Exact file:** upgrade/v2.1.0/UpgradeData.xml    **Type:** XML

```xml
<?xml version="1.0" encoding="UTF-8"?>
<entity-facade-xml type="ext-upgrade">
</entity-facade-xml>
```

### replicant
**Release tag:** v2.0.0-RC1    **Exact file:** upgrade/v2.0.0-RC1/UpgradeData.xml    **Type:** XML

```xml
<?xml version="1.0" encoding="UTF-8"?>
<entity-facade-xml type="ext-upgrade">
</entity-facade-xml>
```

### replicant
**Release tag:** v2.1.0    **Exact file:** upgrade/v2.1.0/UpgradeData.xml    **Type:** XML

```xml
<?xml version="1.0" encoding="UTF-8"?>
<entity-facade-xml type="ext-upgrade">
</entity-facade-xml>
```

### sm-smca-maarg
**Release tag:** v3.0.0-RC1    **Exact file:** upgrade/v3.0.0-RC1/UpgradeData.xml    **Type:** XML

```xml
<?xml version="1.0" encoding="UTF-8"?>
<entity-facade-xml type="ext-upgrade">
</entity-facade-xml>
```

### sm-smca-maarg
**Release tag:** v3.1.0    **Exact file:** upgrade/v3.1.0/UpgradeData.xml    **Type:** XML

```xml
<?xml version="1.0" encoding="UTF-8"?>
<entity-facade-xml type="ext-upgrade">
</entity-facade-xml>
```

### sm-smca-maarg
**Release tag:** v3.1.1    **Exact file:** upgrade/v3.1.1/UpgradeData.xml    **Type:** XML

```xml
<?xml version="1.0" encoding="UTF-8"?>
<entity-facade-xml type="ext-upgrade">
</entity-facade-xml>
```

### sm-smus-maarg
**Release tag:** v2.0.0-RC1    **Exact file:** upgrade/v2.0.0-RC1/UpgradeData.xml    **Type:** XML

```xml
<?xml version="1.0" encoding="UTF-8"?>
<entity-facade-xml type="ext-upgrade">
</entity-facade-xml>
```

### sm-smus-maarg
**Release tag:** v2.1.0    **Exact file:** upgrade/v2.1.0/UpgradeData.xml    **Type:** XML

```xml
<?xml version="1.0" encoding="UTF-8"?>
<entity-facade-xml type="ext-upgrade">
</entity-facade-xml>
```

### hotwax-newera
**Release tag:** v3.0.0-RC1    **Exact file:** upgrade/v3.0.0-RC1/UpgradeData.xml    **Type:** XML

```xml
<?xml version="1.0" encoding="UTF-8"?>
<entity-facade-xml type="ext-upgrade">
</entity-facade-xml>
```

### hotwax-newera
**Release tag:** v3.1.0    **Exact file:** upgrade/v3.1.0/UpgradeData.xml    **Type:** XML

```xml
<?xml version="1.0" encoding="UTF-8"?>
<entity-facade-xml type="ext-upgrade">
</entity-facade-xml>
```

### krewe-maarg
**Release tag:** v2.0.0-RC1    **Exact file:** upgrade/v2.0.0-RC1/UpgradeData.xml    **Type:** XML

```xml
<?xml version="1.0" encoding="UTF-8"?>
<entity-facade-xml type="ext-upgrade">
</entity-facade-xml>
```

### krewe-maarg
**Release tag:** v2.1.0    **Exact file:** upgrade/v2.1.0/UpgradeData.xml    **Type:** XML

```xml
<?xml version="1.0" encoding="UTF-8"?>
<entity-facade-xml type="ext-upgrade">
</entity-facade-xml>
```

### oms-test
**Release tag:** v2.0.0-RC1    **Exact file:** upgrade/v2.0.0-RC1/UpgradeData.xml    **Type:** XML

```xml
<?xml version="1.0" encoding="UTF-8"?>
<entity-facade-xml type="ext-upgrade">
</entity-facade-xml>
```

### oms-test
**Release tag:** v2.1.0    **Exact file:** upgrade/v2.1.0/UpgradeData.xml    **Type:** XML

```xml
<?xml version="1.0" encoding="UTF-8"?>
<entity-facade-xml type="ext-upgrade">
</entity-facade-xml>
```

### oms-test
**Release tag:** v2.1.1    **Exact file:** upgrade/v2.1.1/UpgradeData.xml    **Type:** XML

```xml
<?xml version="1.0" encoding="UTF-8"?>
<entity-facade-xml type="ext-upgrade">
</entity-facade-xml>
```

### notnaked
**Release tag:** v1.0.1    **Exact file:** upgrade/v1.0.1/UpgradeData.xml    **Type:** XML

```xml
<?xml version="1.0" encoding="UTF-8"?>
<entity-facade-xml type="ext-upgrade">
</entity-facade-xml>
```

### notnaked
**Release tag:** v1.1.2    **Exact file:** upgrade/v1.1.2/UpgradeData.xml    **Type:** XML

```xml
<?xml version="1.0" encoding="UTF-8"?>
<entity-facade-xml type="ext-upgrade">
</entity-facade-xml>
```

### notnaked
**Release tag:** v1.2.3    **Exact file:** upgrade/v1.2.3/UpcomingRelease/UpgradeData.xml    **Type:** XML

```xml
<?xml version="1.0" encoding="UTF-8"?>
<entity-facade-xml type="ext-upgrade">
</entity-facade-xml>
```

### notnaked
**Release tag:** v1.2.3    **Exact file:** upgrade/v1.2.3/UpgradeData.xml    **Type:** XML

```xml
<?xml version="1.0" encoding="UTF-8"?>
<entity-facade-xml type="ext-upgrade">
</entity-facade-xml>
```

### notnaked
**Release tag:** v1.3.1    **Exact file:** upgrade/v1.3.1/UpcomingRelease/UpgradeData.xml    **Type:** XML

```xml
<?xml version="1.0" encoding="UTF-8"?>
<entity-facade-xml type="ext-upgrade">
</entity-facade-xml>
```

### notnaked
**Release tag:** v1.3.1    **Exact file:** upgrade/v1.3.1/UpgradeData.xml    **Type:** XML

```xml
<?xml version="1.0" encoding="UTF-8"?>
<entity-facade-xml type="ext-upgrade">
</entity-facade-xml>
```

### notnaked
**Release tag:** v1.3.2    **Exact file:** upgrade/v1.3.2/UpgradeData.xml    **Type:** XML

```xml
<?xml version="1.0" encoding="UTF-8"?>
<entity-facade-xml type="ext-upgrade">
</entity-facade-xml>
```

### notnaked
**Release tag:** v1.3.3    **Exact file:** upgrade/v1.3.3/UpgradeData.xml    **Type:** XML

```xml
<?xml version="1.0" encoding="UTF-8"?>
<entity-facade-xml type="ext-upgrade">
</entity-facade-xml>
```

### notnaked
**Release tag:** v1.4.3    **Exact file:** upgrade/v1.4.3/UpgradeData.xml    **Type:** XML

```xml
<?xml version="1.0" encoding="UTF-8"?>
<entity-facade-xml type="ext-upgrade">
</entity-facade-xml>
```

### notnaked
**Release tag:** v1.8.9    **Exact file:** upgrade/v1.8.9/UpgradeData.xml    **Type:** XML

```xml
<?xml version="1.0" encoding="UTF-8"?>
<entity-facade-xml type="ext-upgrade">
</entity-facade-xml>
```

### notnaked
**Release tag:** v2.0.0-RC1    **Exact file:** upgrade/v2.0.0-RC1/UpgradeData.xml    **Type:** XML

```xml
<?xml version="1.0" encoding="UTF-8"?>
<entity-facade-xml type="ext-upgrade">
</entity-facade-xml>
```

### notnaked
**Release tag:** v2.1.0    **Exact file:** upgrade/v2.1.0/UpgradeData.xml    **Type:** XML

```xml
<?xml version="1.0" encoding="UTF-8"?>
<entity-facade-xml type="ext-upgrade">
</entity-facade-xml>
```

### aftership
**Release tag:** v2.0.0-RC1    **Exact file:** upgrade/v2.0.0-RC1/UpgradeData.xml    **Type:** XML

```xml
<?xml version="1.0" encoding="UTF-8"?>
<entity-facade-xml type="ext-upgrade">
    <moqui.basic.Enumeration enumId="AFTSHP_SCE_WTY" enumTypeId="RETURN_CHANNEL" enumCode="AFTSHP_SCE_WTY" enumName="AfterShip Store Credit Exception Warranty" description="Store Credit Exception Request"/>
    <co.hotwax.integration.IntegrationTypeMapping integrationMappingId="AFTWPGCHNL_SCE_NM" integrationTypeId="AFTSHP_WTY_PAGE_CHNL" mappingKey="Store Credit Exception Request" mappingValue="AFTSHP_SCE_WTY" description="Store Credit Exception Request page name -> AfterShip store credit exception warranty channel"/>
</entity-facade-xml>
```

### aftership
**Release tag:** v2.1.0    **Exact file:** upgrade/v2.1.0/UpgradeData.xml    **Type:** XML

```xml
<?xml version="1.0" encoding="UTF-8"?>
<entity-facade-xml type="ext-upgrade">
</entity-facade-xml>
```

### moqui-mcp
**Release tag:** v1.1.0    **Exact file:** upgrade/v1.1.0/UpgradeData.xml    **Type:** XML

```xml
<?xml version="1.0" encoding="UTF-8"?>
<entity-facade-xml type="ext-upgrade">
</entity-facade-xml>
```

### mephisto-maarg
**Release tag:** v2.0.0-RC1    **Exact file:** upgrade/v2.0.0-RC1/UpgradeData.xml    **Type:** XML

```xml
<?xml version="1.0" encoding="UTF-8"?>
<entity-facade-xml type="ext-upgrade">
</entity-facade-xml>
```

### mephisto-maarg
**Release tag:** v2.1.0    **Exact file:** upgrade/v2.1.0/UpgradeData.xml    **Type:** XML

```xml
<?xml version="1.0" encoding="UTF-8"?>
<entity-facade-xml type="ext-upgrade">
</entity-facade-xml>
```
