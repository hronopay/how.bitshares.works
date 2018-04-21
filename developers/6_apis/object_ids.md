## Objects and IDs

### Contents:
- [Objects Format](/developers/6_apis/object_ids.md#bitshares-objects-format)
- [List of Commonly used Objects](/developers/6_apis/object_ids.md#list-of-commonly-used-objects)
   - [Examples](/developers/6_apis/object_ids.md#examples)
- [Defenitions](/developers/6_apis/object_ids.md#definitions)
   - [Protocol Space (1.x.x)](/developers/6_apis/object_ids.md#protocol-space-1xx)
      - enum graphene::chain::object_type
   - [Implementattion Space (2.x.x)](/developers/6_apis/object_ids.md#implementattion-space-2xx)
      - enum graphene::chain::object_type

***

In contrast to most cryptocurrency wallets, the BitShares 2.0 has a different model to represent the blockchain, its transactions and accounts. 

## Objects

### BitShares Objects Format

    space.type.id
    
    
### List of Commonly used Objects

|	ID  | Object Type |
|----|---------------|
|	1.1.x  | 	base object |
|	1.2.x  | 	account object |
|	1.3.x  | 	asset object |
|	1.4.x  | 	force settlement object |
|	1.5.x  | 	committee member object |
|	1.6.x  | 	witness object |
|	1.7.x  | 	limit order object |
|	1.8.x  | 	call order object |
|	1.9.x  | 	custom object |
|	1.10.x |  	proposal object |
|	1.11.x |  	operation history object |
|	1.12.x |  	withdraw permission object |
|	1.13.x  | 	vesting balance object |
|	1.14.x  | 	worker object |
|	1.15.x |  	balance object |
|	2.0.x |  	global_property_object |
|	2.1.x  | 	dynamic_global_property_object |
|	2.3.x  | 	asset_dynamic_data |
|	2.4.x  | 	asset_bitasset_data |
|	2.5.x  | 	account_balance_object |
|	2.6.x  | 	account_statistics_object |
|	2.7.x |  	transaction_object |
|	2.8.x  | 	block_summary_object |
|	2.9.x  | 	account_transaction_history_object |
|	2.10.x |  	blinded_balance_object |
|	2.11.x |  	chain_property_object |
|	2.12.x |  	witness_schedule_object |
|	2.13.x |  	budget_record_object |
|	2.14.x  | 	special_authority_object |

#### Examples

| Object ID | translates to |
|----------|----------------|
| 1.3.1  | 	asset USD |
| 1.3.0  | 	asset BTS |
| 1.2.\<id\>  | 	user with id <id> |
| 1.6.\<id\>  | 	block signer <id> |
| 1.11.\<id\>  | 	operation with id <id> |
| 2.0.0  | global blockchain parameters |
| 2.1.0  | current blockchain data |
| 1.2.0  | committee-account details |
| 1.3.0  | core asset details |

***

## Definitions
For advanced users that want to deal with the C++ code of graphene, we here list the definition of `object_type` and `impl_object_type`:

### Protocol Space (1.x.x)

List all object types from all namespaces here so they can be easily reflected and displayed in debug output. If a 3rd party wants to extend the core code then they will have to change the `packed_object::type` field from `enum_type to uint16` to avoid warnings when converting packed_objects to/from json.

|  *enum* graphene::chain::object_type |
|----------------------------------------------|
| ---Values--- |
| null_object_type |
| base_object_type |
| account_object_type |
| asset_object_type |
| force_settlement_object_type |
| committee_member_object_type |
| witness_object_type |
| limit_order_object_type |
| call_order_object_type |
| custom_object_type |
| proposal_object_type |
| operation_history_object_type |
| withdraw_permission_object_type |
| vesting_balance_object_type |
| worker_object_type |
| balance_object_type |
| OBJECT_TYPE_COUNT |

Sentry value which contains the number of different object types. 


### Implementattion Space (2.x.x)

| *enum* graphene::chain::impl_object_type |
|----------------------------------------|
|  ---Values---  |
| impl_global_property_object_type |
|  impl_dynamic_global_property_object_type |
|  impl_reserved0_object_type |
| impl_asset_dynamic_data_type |
| impl_asset_bitasset_data_type |
| impl_account_balance_object_type |
|  impl_account_statistics_object_type |
|  impl_transaction_object_type |
|  impl_block_summary_object_type |
|  impl_account_transaction_history_object_type |
|  impl_blinded_balance_object_type |
| impl_chain_property_object_type |
|  impl_witness_schedule_object_type |
|  impl_budget_record_object_type |
| impl_special_authority_object_type |
| impl_buyback_object_type |
|  impl_fba_accumulator_object_type |


***