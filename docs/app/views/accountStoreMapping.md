## Account Store Mapping

*Account Store* is a generic term for either a [Directory](directory) or a [Group](group). 
`Directories` and `Groups` are both are considered *`account stores`* because they both contain, or store,
 `Accounts`. An `Account Store Mapping`, then, represents an `Account Store` mapped (assigned) to an `Application`.

In Stormpath, you control who may login to an `application` by associating (or ‘mapping’) one or more
 `account stores` to an `application`. All of the `accounts` across all of an `application’s` assigned
 `account stores` form the application’s effective *user base*; those `accounts` may login to the `application`.
 If no `account stores` are assigned to an `application`, no `accounts` will be able to login to the `application`.

You control which `account stores` are assigned (mapped) to an `application`, and the order in which they
 are consulted during a `login attempt`, by manipulating an application’s `AccountStoreMapping` resources.

**Since**: 0.1.2

---

<a name="getApplication"></a>
### <span class="member">method</span> getApplication(*[options,]* callback)

Retrieves the associated `Application` and provides it to the specified `callback`.

#### Usage


```javascript
accountStoreMapping.getApplication({expand: 'accounts'}, function(err, app){
  var application = app;
})

```

#### Parameters

<table class="table table-striped table-hover table-curved">
  <thead>
    <tr>
      <th>Parameter</th>
      <th>Type</th>
      <th>Presence</th>
      <th>Description<th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>_`options`_</td>
      <td>`object`</td>
      <td>_optional_</td>
      <td>Name/value pairs to use as query parameters, for example, for [resource expansion](http://docs.stormpath.com/rest/product-guide/#link-expansion).</td>
    </tr>
    <tr>
      <td>`callback`</td>
      <td>`function`</td>
      <td>required</td>
      <td>The callback to execute upon server response. The 1st parameter is an [error](resourceError).  The 2nd parameter is an [Application](application) instance.</td>
    </tr>
  </tbody>
</table>

#### Returns

void; 
If the request fails, the callback's first parameter (`err`) will report the failure.
If the request succeeds, the instance of  [Application](application) will be provided to the `callback` as the callback's second parameter.

---

<a name="setApplication"></a>
### <span class="member">method</span> setApplication(application)

Sets `Application` provided in params as `Account Store Mapping` application.
**This method doesn't generate a request to update `Account Store Mapping`.**

#### Usage


```javascript
var mapping = accountStoreMapping.setApplication(application);
mapping.save(callback)
```

#### Parameters

<table class="table table-striped table-hover table-curved">
  <thead>
    <tr>
      <th>Parameter</th>
      <th>Type</th>
      <th>Presence</th>
      <th>Description<th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>`application`</td>
      <td>object</td>
      <td>required</td>
      <td>The `Application` that will be associated with `Account Store Mapping`.</td>
    </tr>
  </tbody>
</table>

#### Returns

Instance of `AccountStoreMapping`.

---

<a name="getAccountStore"></a>
### <span class="member">method</span> getAccountStore(*[options,]* callback)

Retrieves the associated `Account Store` (`Group` or `Directory`) and provides it to the specified `callback`.

#### Usage


```javascript
accountStoreMapping.getAccountStore({expand: 'accounts'}, function(err, store){
  var accountStore = store;
})

```

#### Parameters

<table class="table table-striped table-hover table-curved">
  <thead>
    <tr>
      <th>Parameter</th>
      <th>Type</th>
      <th>Presence</th>
      <th>Description<th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>_`options`_</td>
      <td>`object`</td>
      <td>_optional_</td>
      <td>Name/value pairs to use as query parameters, for example, for [resource expansion](http://docs.stormpath.com/rest/product-guide/#link-expansion).</td>
    </tr>
    <tr>
      <td>`callback`</td>
      <td>function</td>
      <td>required</td>
      <td>The callback to execute upon server response. The 1st parameter is an [error](resourceError).  The 2nd parameter is an [Directory](directory) or [Group](group) instance.</td>
    </tr>
  </tbody>
</table>

#### Returns

void; 
If the request fails, the callback's first parameter (`err`) will report the failure.
If the request succeeds, the instance of [Directory](directory) or [Group](group) will 
 be provided to the `callback` as the callback's second parameter.

---

<a name="setAccountStore"></a>
### <span class="member">method</span> setAccountStore(accountStore)

Sets `AccountStore` (`Group` or `Directory`) provided in params as `Account Store Mapping` 
 *account store*.
**This method doesn't generate a request to update `Account Store Mapping`.**

#### Usage


```javascript
var mapping = accountStoreMapping.setAccountStore(directory);
mapping.save(callback)
```

#### Parameters

<table class="table table-striped table-hover table-curved">
  <thead>
    <tr>
      <th>Parameter</th>
      <th>Type</th>
      <th>Presence</th>
      <th>Description<th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>`accountStore`</td>
      <td>object</td>
      <td>required</td>
      <td>The `AccountStore` ('Group` or `Directory`) that will be associated with `Account Store Mapping`.</td>
    </tr>
  </tbody>
</table>

#### Returns

Instance of `AccountStoreMapping`.