## Classes

<dl>
<dt><a href="#InlustrisClient">InlustrisClient</a> ⇐ <code><a href="https://discord.js.org/#/docs/main/master/class/Client">Client</a></code></dt>
<dd><p>The base client for Inlustris.</p></dd>
<dt><a href="#BaseRegistry">BaseRegistry</a></dt>
<dd></dd>
<dt><a href="#CommandRegistry">CommandRegistry</a> ⇐ <code><a href="#BaseRegistry">BaseRegistry</a></code></dt>
<dd><p>The registry for holding and loading commands.</p></dd>
<dt><a href="#EventRegistry">EventRegistry</a> ⇐ <code><a href="#BaseRegistry">BaseRegistry</a></code></dt>
<dd><p>The event registry for loading events</p></dd>
<dt><a href="#TaskRegistry">TaskRegistry</a> ⇐ <code><a href="#BaseRegistry">BaseRegistry</a></code></dt>
<dd><p>The registry where tasks are loaded and stored.</p></dd>
<dt><a href="#Schedule">Schedule</a></dt>
<dd><p>The schedule for the schedule plugin.</p></dd>
<dt><a href="#ScheduledTask">ScheduledTask</a></dt>
<dd><p>A scheduled task, used for creating tasks.</p></dd>
<dt><a href="#Base">Base</a></dt>
<dd><p>The base class for all pieces.</p></dd>
<dt><a href="#Command">Command</a> ⇐ <code><a href="#Base">Base</a></code></dt>
<dd><p>Command class for creating commands.</p></dd>
<dt><a href="#Event">Event</a> ⇐ <code><a href="#Base">Base</a></code></dt>
<dd><p>The event class for creating events.</p></dd>
<dt><a href="#Task">Task</a> ⇐ <code><a href="#Base">Base</a></code></dt>
<dd><p>The task class, used for creating tasks.</p></dd>
<dt><a href="#ClientUtil">ClientUtil</a></dt>
<dd><p>Utility methods to use for common tasks.</p></dd>
<dt><a href="#Cron">Cron</a></dt>
<dd><p>Cron utility class, used for creating tasks.</p></dd>
<dt><a href="#InlustrisError">InlustrisError</a> ⇐ <code>Error</code></dt>
<dd><p>An error class used to make error throwing universal.</p></dd>
<dt><a href="#List">List</a> ⇐ <code>Set</code></dt>
<dd><p>A Set with additional utility methods.</p></dd>
<dt><a href="#Type">Type</a></dt>
<dd><p>The class for deep checking types.</p></dd>
<dt><a href="#Util">Util</a></dt>
<dd><p>Internal utility class.</p></dd>
</dl>

## Members

<dl>
<dt><a href="#_Symbol$species">_Symbol$species</a> ⇐ <code>Collection</code></dt>
<dd><p>The base registry for all stores to extend.</p></dd>
</dl>

## Typedefs

<dl>
<dt><a href="#InlustrisPlugin">InlustrisPlugin</a> : <code>Object</code></dt>
<dd><p>The required export to load an external plugin</p></dd>
<dt><a href="#InlustrisOptions">InlustrisOptions</a> : <code><a href="https://discord.js.org/#/docs/main/master/typedef/ClientOptions">ClientOptions</a></code></dt>
<dd><p>Options for a new [InlustrisClient](#InlustrisClient)</p></dd>
<dt><a href="#InternalPlugins">InternalPlugins</a> : <code>string</code></dt>
<dd><p>A list of internal plugins. Calling <code>internals</code> or <code>defaults</code> as a loaded plugin
will load all of them.</p>
<ul>
<li><code>util</code> adds client utility methods.</li>
<li><code>settings</code> adds settings to the client (WIP).</li>
</ul></dd>
<dt><a href="#TimeResolvable">TimeResolvable</a> : <code>Date</code> | <code>number</code> | <code><a href="#Cron">Cron</a></code> | <code>string</code></dt>
<dd><p>Something that is able to be resolved to a time, used for tasks</p></dd>
<dt><a href="#BaseOptions">BaseOptions</a> : <code>Object</code></dt>
<dd><p>The base options for a module</p></dd>
</dl>

<a name="InlustrisClient"></a>

## InlustrisClient ⇐ [<code>Client</code>](https://discord.js.org/#/docs/main/master/class/Client)
<p>The base client for Inlustris.</p>

**Kind**: global class  
**Extends**: [<code>Client</code>](https://discord.js.org/#/docs/main/master/class/Client)  

* [InlustrisClient](#InlustrisClient) ⇐ [<code>Client</code>](https://discord.js.org/#/docs/main/master/class/Client)
    * [new InlustrisClient([options])](#new_InlustrisClient_new)
    * [.util](#InlustrisClient+util) : [<code>ClientUtil</code>](#ClientUtil)
    * [.application](#InlustrisClient+application) : [<code>ClientApplication</code>](https://discord.js.org/#/docs/main/master/class/ClientApplication)
    * [.events](#InlustrisClient+events) : [<code>EventRegistry</code>](#EventRegistry)
    * [.loaded](#InlustrisClient+loaded) : <code>boolean</code>
    * [.tasks](#InlustrisClient+tasks) : [<code>TaskRegistry</code>](#TaskRegistry)
    * [.schedule](#InlustrisClient+schedule) : [<code>Schedule</code>](#Schedule)
    * [.ready](#InlustrisClient+ready) : <code>boolean</code>
    * [.owners](#InlustrisClient+owners) : [<code>List.&lt;User&gt;</code>](https://discord.js.org/#/docs/main/master/class/User)
    * [.plugins](#InlustrisClient+plugins) : <code>List.&lt;string&gt;</code>
    * [.text](#InlustrisClient+text) : <code>Collection.&lt;string, TextChannel&gt;</code>
    * [.voiceChannels](#InlustrisClient+voiceChannels) : <code>Collection.&lt;string, VoiceChannel&gt;</code>
    * [.news](#InlustrisClient+news) : <code>Collection.&lt;string, NewsChannel&gt;</code>
    * [.store](#InlustrisClient+store) : <code>Collection.&lt;string, StoreChannel&gt;</code>
    * [.category](#InlustrisClient+category) : <code>Collection.&lt;string, CategoryChannel&gt;</code>
    * [.dm](#InlustrisClient+dm) : <code>Collection.&lt;string, DMChannel&gt;</code>
    * [.me](#InlustrisClient+me) : <code>Collection.&lt;string, ?GuildMember&gt;</code>
    * [.fetchApplication()](#InlustrisClient+fetchApplication) ⇒ [<code>Promise.&lt;ClientApplication&gt;</code>](https://discord.js.org/#/docs/main/master/class/ClientApplication)
    * ~~[.login()](#InlustrisClient+login)~~
    * [.start()](#InlustrisClient+start) ⇒ <code>Promise.&lt;string&gt;</code>
    * [.load()](#InlustrisClient+load) ⇒ <code>Promise.&lt;List.&lt;string&gt;&gt;</code>
    * [.use(mod)](#InlustrisClient+use) ⇒ [<code>InlustrisClient</code>](#InlustrisClient)
    * [.isOwner(user)](#InlustrisClient+isOwner) ⇒ <code>boolean</code>
    * [.@@iterator()](#InlustrisClient+@@iterator) ⇒ <code>Iterator.&lt;string&gt;</code>
    * ["baseEnabled" (base)](#InlustrisClient+event_baseEnabled)
    * ["baseDisabled" (base)](#InlustrisClient+event_baseDisabled)
    * ["clientReady"](#InlustrisClient+event_clientReady)
    * ["baseUnloaded" (base)](#InlustrisClient+event_baseUnloaded)

<a name="new_InlustrisClient_new"></a>

### new InlustrisClient([options])
<p>Creates a new client.</p>


| Param | Type | Default | Description |
| --- | --- | --- | --- |
| [options] | [<code>InlustrisOptions</code>](#InlustrisOptions) | <code>{}</code> | <p>Options to use when loading the client.</p> |

<a name="InlustrisClient+util"></a>

### inlustrisClient.util : [<code>ClientUtil</code>](#ClientUtil)
<p>A [ClientUtil](#ClientUtil) to use, will only be loaded if <code>internals</code>, <code>defaults</code>, or <code>util</code> is specified in [InlustrisOptions#plugins](InlustrisOptions#plugins) or used with [use](#InlustrisClient+use)</p>

**Kind**: instance property of [<code>InlustrisClient</code>](#InlustrisClient)  
<a name="InlustrisClient+application"></a>

### inlustrisClient.application : [<code>ClientApplication</code>](https://discord.js.org/#/docs/main/master/class/ClientApplication)
<p>The application of the client</p>

**Kind**: instance property of [<code>InlustrisClient</code>](#InlustrisClient)  
<a name="InlustrisClient+events"></a>

### inlustrisClient.events : [<code>EventRegistry</code>](#EventRegistry)
<p>The event registry for all the events</p>

**Kind**: instance property of [<code>InlustrisClient</code>](#InlustrisClient)  
**Read only**: true  
<a name="InlustrisClient+loaded"></a>

### inlustrisClient.loaded : <code>boolean</code>
<p>Whether the client has loaded all available plugins</p>

**Kind**: instance property of [<code>InlustrisClient</code>](#InlustrisClient)  
<a name="InlustrisClient+tasks"></a>

### inlustrisClient.tasks : [<code>TaskRegistry</code>](#TaskRegistry)
<p>The registry where tasks are stored, only applied if <code>schedule</code>, <code>tasks</code>, <code>internals</code>, or <code>defaults</code> is a loaded plugin</p>

**Kind**: instance property of [<code>InlustrisClient</code>](#InlustrisClient)  
<a name="InlustrisClient+schedule"></a>

### inlustrisClient.schedule : [<code>Schedule</code>](#Schedule)
<p>The schedule for the tasks, only applied if <code>schedule</code>, <code>tasks</code>, <code>internals</code>, or <code>defaults</code> is a loaded plugin</p>

**Kind**: instance property of [<code>InlustrisClient</code>](#InlustrisClient)  
<a name="InlustrisClient+ready"></a>

### inlustrisClient.ready : <code>boolean</code>
<p>Whether the client is ready. Used internally for several things</p>

**Kind**: instance property of [<code>InlustrisClient</code>](#InlustrisClient)  
<a name="InlustrisClient+owners"></a>

### inlustrisClient.owners : [<code>List.&lt;User&gt;</code>](https://discord.js.org/#/docs/main/master/class/User)
<p>The owners of the client, will only have one until teams support is added</p>

**Kind**: instance property of [<code>InlustrisClient</code>](#InlustrisClient)  
**Read only**: true  
<a name="InlustrisClient+plugins"></a>

### inlustrisClient.plugins : <code>List.&lt;string&gt;</code>
<p>The plugins that will be loaded when the client starts</p>

**Kind**: instance property of [<code>InlustrisClient</code>](#InlustrisClient)  
**Read only**: true  
<a name="InlustrisClient+text"></a>

### inlustrisClient.text : <code>Collection.&lt;string, TextChannel&gt;</code>
<p>All the text channels the client can see</p>

**Kind**: instance property of [<code>InlustrisClient</code>](#InlustrisClient)  
**Read only**: true  
<a name="InlustrisClient+voiceChannels"></a>

### inlustrisClient.voiceChannels : <code>Collection.&lt;string, VoiceChannel&gt;</code>
<p>All the voice channels the client can see (named this was as Client#voice is the <code>ClientVoiceManager</code>)</p>

**Kind**: instance property of [<code>InlustrisClient</code>](#InlustrisClient)  
**Read only**: true  
<a name="InlustrisClient+news"></a>

### inlustrisClient.news : <code>Collection.&lt;string, NewsChannel&gt;</code>
<p>All the news channels the client can see</p>

**Kind**: instance property of [<code>InlustrisClient</code>](#InlustrisClient)  
**Read only**: true  
<a name="InlustrisClient+store"></a>

### inlustrisClient.store : <code>Collection.&lt;string, StoreChannel&gt;</code>
<p>All the store channels the client can see</p>

**Kind**: instance property of [<code>InlustrisClient</code>](#InlustrisClient)  
**Read only**: true  
<a name="InlustrisClient+category"></a>

### inlustrisClient.category : <code>Collection.&lt;string, CategoryChannel&gt;</code>
<p>All the category channels the client can see</p>

**Kind**: instance property of [<code>InlustrisClient</code>](#InlustrisClient)  
**Read only**: true  
<a name="InlustrisClient+dm"></a>

### inlustrisClient.dm : <code>Collection.&lt;string, DMChannel&gt;</code>
<p>All the DM channels the client can see</p>

**Kind**: instance property of [<code>InlustrisClient</code>](#InlustrisClient)  
**Read only**: true  
<a name="InlustrisClient+me"></a>

### inlustrisClient.me : <code>Collection.&lt;string, ?GuildMember&gt;</code>
<p>A collection of all the <code>Guild#me</code> instances, mapped by Guild ID</p>

**Kind**: instance property of [<code>InlustrisClient</code>](#InlustrisClient)  
**Read only**: true  
<a name="InlustrisClient+fetchApplication"></a>

### inlustrisClient.fetchApplication() ⇒ [<code>Promise.&lt;ClientApplication&gt;</code>](https://discord.js.org/#/docs/main/master/class/ClientApplication)
<p>Does the same as <a href="https://discord.js.org/#/docs/main/master/class/Client?scrollTo=fetchApplication">Client#fetchApplication()</a> but attaches the resolved value to [application](#InlustrisClient+application)</p>

**Kind**: instance method of [<code>InlustrisClient</code>](#InlustrisClient)  
<a name="InlustrisClient+login"></a>

### ~~inlustrisClient.login()~~
***Deprecated***

<p>Deprecated method, throws an error on use, use [start](#InlustrisClient+start) to start the client</p>

**Kind**: instance method of [<code>InlustrisClient</code>](#InlustrisClient)  
**Throws**:

- [<code>InlustrisError</code>](#InlustrisError) 

<a name="InlustrisClient+start"></a>

### inlustrisClient.start() ⇒ <code>Promise.&lt;string&gt;</code>
<p>Loads and initializes the plugins, and logs the client in.</p>

**Kind**: instance method of [<code>InlustrisClient</code>](#InlustrisClient)  
<a name="InlustrisClient+load"></a>

### inlustrisClient.load() ⇒ <code>Promise.&lt;List.&lt;string&gt;&gt;</code>
<p>Loads all the plugins called in the options or with <code>InlustrisClient#use</code>.</p>

**Kind**: instance method of [<code>InlustrisClient</code>](#InlustrisClient)  
<a name="InlustrisClient+use"></a>

### inlustrisClient.use(mod) ⇒ [<code>InlustrisClient</code>](#InlustrisClient)
<p>Designates a plugin to load, will be loaded on start.</p>

**Kind**: instance method of [<code>InlustrisClient</code>](#InlustrisClient)  

| Param | Type | Description |
| --- | --- | --- |
| mod | <code>string</code> | <p>The name of a plugin to load, will be required if it's external</p> |

<a name="InlustrisClient+isOwner"></a>

### inlustrisClient.isOwner(user) ⇒ <code>boolean</code>
<p>Checks if the given user is an owner of the bot.</p>

**Kind**: instance method of [<code>InlustrisClient</code>](#InlustrisClient)  

| Param | Type | Description |
| --- | --- | --- |
| user | [<code>UserResolvable</code>](https://discord.js.org/#/docs/main/master/typedef/UserResolvable) | <p>The user to check</p> |

<a name="InlustrisClient+@@iterator"></a>

### inlustrisClient.@@iterator() ⇒ <code>Iterator.&lt;string&gt;</code>
<p>An iterator containing the list of plugins.</p>

**Kind**: instance method of [<code>InlustrisClient</code>](#InlustrisClient)  
<a name="InlustrisClient+event_baseEnabled"></a>

### "baseEnabled" (base)
<p>Emitted when a base is enabled.</p>

**Kind**: event emitted by [<code>InlustrisClient</code>](#InlustrisClient)  

| Param | Type | Description |
| --- | --- | --- |
| base | [<code>Base</code>](#Base) | <p>The base that was enabled</p> |

<a name="InlustrisClient+event_baseDisabled"></a>

### "baseDisabled" (base)
<p>Emitted when a base is disabled.</p>

**Kind**: event emitted by [<code>InlustrisClient</code>](#InlustrisClient)  

| Param | Type | Description |
| --- | --- | --- |
| base | [<code>Base</code>](#Base) | <p>The base that was disabled</p> |

<a name="InlustrisClient+event_clientReady"></a>

### "clientReady"
<p>Emitted when the client is ready. Should be listened to over <code>Client#ready</code>
as Inlustris uses that internallly to initialize the client once Discord data
is ready.</p>

**Kind**: event emitted by [<code>InlustrisClient</code>](#InlustrisClient)  
<a name="InlustrisClient+event_baseUnloaded"></a>

### "baseUnloaded" (base)
<p>Emitted when a base is unloaded.</p>

**Kind**: event emitted by [<code>InlustrisClient</code>](#InlustrisClient)  

| Param | Type | Description |
| --- | --- | --- |
| base | [<code>Base</code>](#Base) | <p>The base that was disabled</p> |

<a name="BaseRegistry"></a>

## BaseRegistry
**Kind**: global class  

* [BaseRegistry](#BaseRegistry)
    * [new BaseRegistry(client, name, holds)](#new_BaseRegistry_new)
    * [.holds](#BaseRegistry+holds) : [<code>InlustrisClient</code>](#InlustrisClient)
    * [.name](#BaseRegistry+name) : <code>string</code>
    * [.holds](#BaseRegistry+holds) : [<code>Base</code>](#Base)
    * [.userDirectory](#BaseRegistry+userDirectory) : <code>string</code>
    * [.registerCoreDirectory(directory)](#BaseRegistry+registerCoreDirectory) ⇒ <code>this</code>
    * [.loadAll()](#BaseRegistry+loadAll) ⇒ <code>Promise.&lt;number&gt;</code>
    * [.load(directory, file)](#BaseRegistry+load) ⇒ [<code>Base</code>](#Base)
    * [.add(base)](#BaseRegistry+add) ⇒ [<code>Base</code>](#Base)

<a name="new_BaseRegistry_new"></a>

### new BaseRegistry(client, name, holds)
<p>Creates a new BaseRegistry.</p>


| Param | Type | Description |
| --- | --- | --- |
| client | [<code>InlustrisClient</code>](#InlustrisClient) | <p>The client</p> |
| name | <code>string</code> | <p>The name of the registry</p> |
| holds | <code>function</code> | <p>The class that the registry will use to create instances</p> |

<a name="BaseRegistry+holds"></a>

### baseRegistry.holds : [<code>InlustrisClient</code>](#InlustrisClient)
<p>The client that this Registry is for</p>

**Kind**: instance property of [<code>BaseRegistry</code>](#BaseRegistry)  
**Read only**: true  
<a name="BaseRegistry+name"></a>

### baseRegistry.name : <code>string</code>
<p>The name of the Registry</p>

**Kind**: instance property of [<code>BaseRegistry</code>](#BaseRegistry)  
**Read only**: true  
<a name="BaseRegistry+holds"></a>

### baseRegistry.holds : [<code>Base</code>](#Base)
<p>What this Registry holds</p>

**Kind**: instance property of [<code>BaseRegistry</code>](#BaseRegistry)  
**Read only**: true  
<a name="BaseRegistry+userDirectory"></a>

### baseRegistry.userDirectory : <code>string</code>
<p>The directory where the bases are found</p>

**Kind**: instance property of [<code>BaseRegistry</code>](#BaseRegistry)  
<a name="BaseRegistry+registerCoreDirectory"></a>

### baseRegistry.registerCoreDirectory(directory) ⇒ <code>this</code>
<p>Registers a core directory.</p>

**Kind**: instance method of [<code>BaseRegistry</code>](#BaseRegistry)  

| Param | Type | Description |
| --- | --- | --- |
| directory | <code>string</code> | <p>The directory to register</p> |

<a name="BaseRegistry+loadAll"></a>

### baseRegistry.loadAll() ⇒ <code>Promise.&lt;number&gt;</code>
<p>Loads all the bases found in the core directories.</p>

**Kind**: instance method of [<code>BaseRegistry</code>](#BaseRegistry)  
<a name="BaseRegistry+load"></a>

### baseRegistry.load(directory, file) ⇒ [<code>Base</code>](#Base)
<p>Loads a base into the registry.</p>

**Kind**: instance method of [<code>BaseRegistry</code>](#BaseRegistry)  

| Param | Type | Description |
| --- | --- | --- |
| directory | <code>string</code> | <p>The directory of the base</p> |
| file | <code>Array.&lt;string&gt;</code> | <p>The file location of the base</p> |

<a name="BaseRegistry+add"></a>

### baseRegistry.add(base) ⇒ [<code>Base</code>](#Base)
<p>Adds a base to the registry.</p>

**Kind**: instance method of [<code>BaseRegistry</code>](#BaseRegistry)  

| Param | Type | Description |
| --- | --- | --- |
| base | [<code>Base</code>](#Base) | <p>The base to be added</p> |

<a name="CommandRegistry"></a>

## CommandRegistry ⇐ [<code>BaseRegistry</code>](#BaseRegistry)
<p>The registry for holding and loading commands.</p>

**Kind**: global class  
**Extends**: [<code>BaseRegistry</code>](#BaseRegistry)  

* [CommandRegistry](#CommandRegistry) ⇐ [<code>BaseRegistry</code>](#BaseRegistry)
    * [.holds](#BaseRegistry+holds) : [<code>InlustrisClient</code>](#InlustrisClient)
    * [.name](#BaseRegistry+name) : <code>string</code>
    * [.userDirectory](#BaseRegistry+userDirectory) : <code>string</code>
    * [.add(base)](#CommandRegistry+add) ⇒ [<code>Command</code>](#Command)
    * [.get(key)](#CommandRegistry+get) ⇒ [<code>Command</code>](#Command)
    * [.has(name)](#CommandRegistry+has) ⇒ <code>boolean</code>
    * [.delete(key)](#CommandRegistry+delete) ⇒ <code>boolean</code>
    * [.clear()](#CommandRegistry+clear) ⇒ <code>void</code>
    * [.registerCoreDirectory(directory)](#BaseRegistry+registerCoreDirectory) ⇒ <code>this</code>
    * [.loadAll()](#BaseRegistry+loadAll) ⇒ <code>Promise.&lt;number&gt;</code>
    * [.load(directory, file)](#BaseRegistry+load) ⇒ [<code>Base</code>](#Base)

<a name="BaseRegistry+holds"></a>

### commandRegistry.holds : [<code>InlustrisClient</code>](#InlustrisClient)
<p>The client that this Registry is for</p>

**Kind**: instance property of [<code>CommandRegistry</code>](#CommandRegistry)  
**Overrides**: [<code>holds</code>](#BaseRegistry+holds)  
**Read only**: true  
<a name="BaseRegistry+name"></a>

### commandRegistry.name : <code>string</code>
<p>The name of the Registry</p>

**Kind**: instance property of [<code>CommandRegistry</code>](#CommandRegistry)  
**Overrides**: [<code>name</code>](#BaseRegistry+name)  
**Read only**: true  
<a name="BaseRegistry+userDirectory"></a>

### commandRegistry.userDirectory : <code>string</code>
<p>The directory where the bases are found</p>

**Kind**: instance property of [<code>CommandRegistry</code>](#CommandRegistry)  
**Overrides**: [<code>userDirectory</code>](#BaseRegistry+userDirectory)  
<a name="CommandRegistry+add"></a>

### commandRegistry.add(base) ⇒ [<code>Command</code>](#Command)
<p>Adds a Command to the registry, and it's aliases.</p>

**Kind**: instance method of [<code>CommandRegistry</code>](#CommandRegistry)  
**Overrides**: [<code>add</code>](#BaseRegistry+add)  

| Param | Type | Description |
| --- | --- | --- |
| base | [<code>Command</code>](#Command) | <p>The command to add</p> |

<a name="CommandRegistry+get"></a>

### commandRegistry.get(key) ⇒ [<code>Command</code>](#Command)
<p>Gets a command by ID or an alias.</p>

**Kind**: instance method of [<code>CommandRegistry</code>](#CommandRegistry)  

| Param | Type | Description |
| --- | --- | --- |
| key | <code>string</code> | <p>The command ID or alias</p> |

<a name="CommandRegistry+has"></a>

### commandRegistry.has(name) ⇒ <code>boolean</code>
<p>Whether or not an ID or alias is in the command registry.</p>

**Kind**: instance method of [<code>CommandRegistry</code>](#CommandRegistry)  

| Param | Type | Description |
| --- | --- | --- |
| name | <code>string</code> | <p>The ID or an alias of the command</p> |

<a name="CommandRegistry+delete"></a>

### commandRegistry.delete(key) ⇒ <code>boolean</code>
<p>Deletes a command from the registry, and clears it's aliases.</p>

**Kind**: instance method of [<code>CommandRegistry</code>](#CommandRegistry)  

| Param | Type | Description |
| --- | --- | --- |
| key | <code>string</code> | <p>The ID or an alias of the command</p> |

<a name="CommandRegistry+clear"></a>

### commandRegistry.clear() ⇒ <code>void</code>
<p>Clears the registry and the aliases.</p>

**Kind**: instance method of [<code>CommandRegistry</code>](#CommandRegistry)  
<a name="BaseRegistry+registerCoreDirectory"></a>

### commandRegistry.registerCoreDirectory(directory) ⇒ <code>this</code>
<p>Registers a core directory.</p>

**Kind**: instance method of [<code>CommandRegistry</code>](#CommandRegistry)  
**Overrides**: [<code>registerCoreDirectory</code>](#BaseRegistry+registerCoreDirectory)  

| Param | Type | Description |
| --- | --- | --- |
| directory | <code>string</code> | <p>The directory to register</p> |

<a name="BaseRegistry+loadAll"></a>

### commandRegistry.loadAll() ⇒ <code>Promise.&lt;number&gt;</code>
<p>Loads all the bases found in the core directories.</p>

**Kind**: instance method of [<code>CommandRegistry</code>](#CommandRegistry)  
**Overrides**: [<code>loadAll</code>](#BaseRegistry+loadAll)  
<a name="BaseRegistry+load"></a>

### commandRegistry.load(directory, file) ⇒ [<code>Base</code>](#Base)
<p>Loads a base into the registry.</p>

**Kind**: instance method of [<code>CommandRegistry</code>](#CommandRegistry)  
**Overrides**: [<code>load</code>](#BaseRegistry+load)  

| Param | Type | Description |
| --- | --- | --- |
| directory | <code>string</code> | <p>The directory of the base</p> |
| file | <code>Array.&lt;string&gt;</code> | <p>The file location of the base</p> |

<a name="EventRegistry"></a>

## EventRegistry ⇐ [<code>BaseRegistry</code>](#BaseRegistry)
<p>The event registry for loading events</p>

**Kind**: global class  
**Extends**: [<code>BaseRegistry</code>](#BaseRegistry)  

* [EventRegistry](#EventRegistry) ⇐ [<code>BaseRegistry</code>](#BaseRegistry)
    * [.holds](#BaseRegistry+holds) : [<code>InlustrisClient</code>](#InlustrisClient)
    * [.name](#BaseRegistry+name) : <code>string</code>
    * [.userDirectory](#BaseRegistry+userDirectory) : <code>string</code>
    * [.load(directory, file)](#EventRegistry+load) ⇒ [<code>Event</code>](#Event)
    * [.clear()](#EventRegistry+clear) ⇒ <code>void</code>
    * [.delete(id)](#EventRegistry+delete) ⇒ <code>boolean</code>
    * [.add(base)](#EventRegistry+add) ⇒ [<code>Event</code>](#Event)
    * [.registerCoreDirectory(directory)](#BaseRegistry+registerCoreDirectory) ⇒ <code>this</code>
    * [.loadAll()](#BaseRegistry+loadAll) ⇒ <code>Promise.&lt;number&gt;</code>

<a name="BaseRegistry+holds"></a>

### eventRegistry.holds : [<code>InlustrisClient</code>](#InlustrisClient)
<p>The client that this Registry is for</p>

**Kind**: instance property of [<code>EventRegistry</code>](#EventRegistry)  
**Overrides**: [<code>holds</code>](#BaseRegistry+holds)  
**Read only**: true  
<a name="BaseRegistry+name"></a>

### eventRegistry.name : <code>string</code>
<p>The name of the Registry</p>

**Kind**: instance property of [<code>EventRegistry</code>](#EventRegistry)  
**Overrides**: [<code>name</code>](#BaseRegistry+name)  
**Read only**: true  
<a name="BaseRegistry+userDirectory"></a>

### eventRegistry.userDirectory : <code>string</code>
<p>The directory where the bases are found</p>

**Kind**: instance property of [<code>EventRegistry</code>](#EventRegistry)  
**Overrides**: [<code>userDirectory</code>](#BaseRegistry+userDirectory)  
<a name="EventRegistry+load"></a>

### eventRegistry.load(directory, file) ⇒ [<code>Event</code>](#Event)
<p>Loads the event, and checks if it's already been ran.</p>

**Kind**: instance method of [<code>EventRegistry</code>](#EventRegistry)  
**Overrides**: [<code>load</code>](#BaseRegistry+load)  

| Param | Type | Description |
| --- | --- | --- |
| directory | <code>string</code> | <p>The directory to load from</p> |
| file | <code>Array.&lt;string&gt;</code> | <p>The file location of the event</p> |

<a name="EventRegistry+clear"></a>

### eventRegistry.clear() ⇒ <code>void</code>
<p>Clears the events.</p>

**Kind**: instance method of [<code>EventRegistry</code>](#EventRegistry)  
<a name="EventRegistry+delete"></a>

### eventRegistry.delete(id) ⇒ <code>boolean</code>
<p>Unlistens to and deletes an event.</p>

**Kind**: instance method of [<code>EventRegistry</code>](#EventRegistry)  

| Param | Type | Description |
| --- | --- | --- |
| id | <code>string</code> | <p>The ID of the event</p> |

<a name="EventRegistry+add"></a>

### eventRegistry.add(base) ⇒ [<code>Event</code>](#Event)
<p>Adds an event to the registry, and attaches it to an event emitter.</p>

**Kind**: instance method of [<code>EventRegistry</code>](#EventRegistry)  
**Overrides**: [<code>add</code>](#BaseRegistry+add)  

| Param | Type | Description |
| --- | --- | --- |
| base | [<code>Event</code>](#Event) | <p>The event to load</p> |

<a name="BaseRegistry+registerCoreDirectory"></a>

### eventRegistry.registerCoreDirectory(directory) ⇒ <code>this</code>
<p>Registers a core directory.</p>

**Kind**: instance method of [<code>EventRegistry</code>](#EventRegistry)  
**Overrides**: [<code>registerCoreDirectory</code>](#BaseRegistry+registerCoreDirectory)  

| Param | Type | Description |
| --- | --- | --- |
| directory | <code>string</code> | <p>The directory to register</p> |

<a name="BaseRegistry+loadAll"></a>

### eventRegistry.loadAll() ⇒ <code>Promise.&lt;number&gt;</code>
<p>Loads all the bases found in the core directories.</p>

**Kind**: instance method of [<code>EventRegistry</code>](#EventRegistry)  
**Overrides**: [<code>loadAll</code>](#BaseRegistry+loadAll)  
<a name="TaskRegistry"></a>

## TaskRegistry ⇐ [<code>BaseRegistry</code>](#BaseRegistry)
<p>The registry where tasks are loaded and stored.</p>

**Kind**: global class  
**Extends**: [<code>BaseRegistry</code>](#BaseRegistry)  

* [TaskRegistry](#TaskRegistry) ⇐ [<code>BaseRegistry</code>](#BaseRegistry)
    * [.holds](#BaseRegistry+holds) : [<code>InlustrisClient</code>](#InlustrisClient)
    * [.name](#BaseRegistry+name) : <code>string</code>
    * [.userDirectory](#BaseRegistry+userDirectory) : <code>string</code>
    * [.registerCoreDirectory(directory)](#BaseRegistry+registerCoreDirectory) ⇒ <code>this</code>
    * [.loadAll()](#BaseRegistry+loadAll) ⇒ <code>Promise.&lt;number&gt;</code>
    * [.load(directory, file)](#BaseRegistry+load) ⇒ [<code>Base</code>](#Base)
    * [.add(base)](#BaseRegistry+add) ⇒ [<code>Base</code>](#Base)

<a name="BaseRegistry+holds"></a>

### taskRegistry.holds : [<code>InlustrisClient</code>](#InlustrisClient)
<p>The client that this Registry is for</p>

**Kind**: instance property of [<code>TaskRegistry</code>](#TaskRegistry)  
**Overrides**: [<code>holds</code>](#BaseRegistry+holds)  
**Read only**: true  
<a name="BaseRegistry+name"></a>

### taskRegistry.name : <code>string</code>
<p>The name of the Registry</p>

**Kind**: instance property of [<code>TaskRegistry</code>](#TaskRegistry)  
**Overrides**: [<code>name</code>](#BaseRegistry+name)  
**Read only**: true  
<a name="BaseRegistry+userDirectory"></a>

### taskRegistry.userDirectory : <code>string</code>
<p>The directory where the bases are found</p>

**Kind**: instance property of [<code>TaskRegistry</code>](#TaskRegistry)  
**Overrides**: [<code>userDirectory</code>](#BaseRegistry+userDirectory)  
<a name="BaseRegistry+registerCoreDirectory"></a>

### taskRegistry.registerCoreDirectory(directory) ⇒ <code>this</code>
<p>Registers a core directory.</p>

**Kind**: instance method of [<code>TaskRegistry</code>](#TaskRegistry)  
**Overrides**: [<code>registerCoreDirectory</code>](#BaseRegistry+registerCoreDirectory)  

| Param | Type | Description |
| --- | --- | --- |
| directory | <code>string</code> | <p>The directory to register</p> |

<a name="BaseRegistry+loadAll"></a>

### taskRegistry.loadAll() ⇒ <code>Promise.&lt;number&gt;</code>
<p>Loads all the bases found in the core directories.</p>

**Kind**: instance method of [<code>TaskRegistry</code>](#TaskRegistry)  
**Overrides**: [<code>loadAll</code>](#BaseRegistry+loadAll)  
<a name="BaseRegistry+load"></a>

### taskRegistry.load(directory, file) ⇒ [<code>Base</code>](#Base)
<p>Loads a base into the registry.</p>

**Kind**: instance method of [<code>TaskRegistry</code>](#TaskRegistry)  
**Overrides**: [<code>load</code>](#BaseRegistry+load)  

| Param | Type | Description |
| --- | --- | --- |
| directory | <code>string</code> | <p>The directory of the base</p> |
| file | <code>Array.&lt;string&gt;</code> | <p>The file location of the base</p> |

<a name="BaseRegistry+add"></a>

### taskRegistry.add(base) ⇒ [<code>Base</code>](#Base)
<p>Adds a base to the registry.</p>

**Kind**: instance method of [<code>TaskRegistry</code>](#TaskRegistry)  
**Overrides**: [<code>add</code>](#BaseRegistry+add)  

| Param | Type | Description |
| --- | --- | --- |
| base | [<code>Base</code>](#Base) | <p>The base to be added</p> |

<a name="Schedule"></a>

## Schedule
<p>The schedule for the schedule plugin.</p>

**Kind**: global class  

* [Schedule](#Schedule)
    * [.client](#Schedule+client) : [<code>InlustrisClient</code>](#InlustrisClient)
    * [.tasks](#Schedule+tasks) : [<code>Array.&lt;ScheduledTask&gt;</code>](#ScheduledTask)
    * [.init()](#Schedule+init) ⇒ <code>Promise.&lt;void&gt;</code>
    * [.create(taskName, time, [options])](#Schedule+create) ⇒ [<code>Promise.&lt;ScheduledTask&gt;</code>](#ScheduledTask)
    * [.clear()](#Schedule+clear) ⇒ <code>void</code>
    * [.get(id)](#Schedule+get) ⇒ [<code>ScheduledTask</code>](#ScheduledTask)
    * [.next()](#Schedule+next) ⇒ [<code>ScheduledTask</code>](#ScheduledTask)
    * [.delete(id)](#Schedule+delete) ⇒ [<code>Promise.&lt;Schedule&gt;</code>](#Schedule)
    * [._insert(task)](#Schedule+_insert) ⇒ [<code>ScheduledTask</code>](#ScheduledTask)
    * [.execute()](#Schedule+execute) ⇒ <code>Promise.&lt;void&gt;</code>
    * [.@@iterator()](#Schedule+@@iterator) ⇒ [<code>Iterator.&lt;ScheduledTask&gt;</code>](#ScheduledTask)

<a name="Schedule+client"></a>

### schedule.client : [<code>InlustrisClient</code>](#InlustrisClient)
<p>The client</p>

**Kind**: instance property of [<code>Schedule</code>](#Schedule)  
<a name="Schedule+tasks"></a>

### schedule.tasks : [<code>Array.&lt;ScheduledTask&gt;</code>](#ScheduledTask)
<p>The tasks that have been set</p>

**Kind**: instance property of [<code>Schedule</code>](#Schedule)  
<a name="Schedule+init"></a>

### schedule.init() ⇒ <code>Promise.&lt;void&gt;</code>
<p>Initializes the schedule, placeholder while I work on settings.
Called when the client is ready.</p>

**Kind**: instance method of [<code>Schedule</code>](#Schedule)  
<a name="Schedule+create"></a>

### schedule.create(taskName, time, [options]) ⇒ [<code>Promise.&lt;ScheduledTask&gt;</code>](#ScheduledTask)
<p>Creates a task and adds it to the schedule.</p>

**Kind**: instance method of [<code>Schedule</code>](#Schedule)  

| Param | Type | Description |
| --- | --- | --- |
| taskName | <code>string</code> | <p>The name of the task in the task registry</p> |
| time | <code>string</code> \| <code>number</code> \| <code>Date</code> | <p>The time for the task</p> |
| [options] | <code>ScheduledTaskOptions</code> | <p>The options for the task</p> |

<a name="Schedule+clear"></a>

### schedule.clear() ⇒ <code>void</code>
<p>Clears the tasks.</p>

**Kind**: instance method of [<code>Schedule</code>](#Schedule)  
<a name="Schedule+get"></a>

### schedule.get(id) ⇒ [<code>ScheduledTask</code>](#ScheduledTask)
<p>Gets a task by ID.</p>

**Kind**: instance method of [<code>Schedule</code>](#Schedule)  

| Param | Type | Description |
| --- | --- | --- |
| id | <code>string</code> | <p>The ID of the task</p> |

<a name="Schedule+next"></a>

### schedule.next() ⇒ [<code>ScheduledTask</code>](#ScheduledTask)
<p>The next task in the schedule.</p>

**Kind**: instance method of [<code>Schedule</code>](#Schedule)  
<a name="Schedule+delete"></a>

### schedule.delete(id) ⇒ [<code>Promise.&lt;Schedule&gt;</code>](#Schedule)
<p>Deletes a task from the schedule.</p>

**Kind**: instance method of [<code>Schedule</code>](#Schedule)  

| Param | Type | Description |
| --- | --- | --- |
| id | <code>string</code> | <p>The ID of the task</p> |

<a name="Schedule+_insert"></a>

### schedule.\_insert(task) ⇒ [<code>ScheduledTask</code>](#ScheduledTask)
<p>Inserts a task into the schedule.</p>

**Kind**: instance method of [<code>Schedule</code>](#Schedule)  

| Param | Type | Description |
| --- | --- | --- |
| task | [<code>ScheduledTask</code>](#ScheduledTask) | <p>The task to insert</p> |

<a name="Schedule+execute"></a>

### schedule.execute() ⇒ <code>Promise.&lt;void&gt;</code>
<p>Executes tasks that need to be executed.</p>

**Kind**: instance method of [<code>Schedule</code>](#Schedule)  
<a name="Schedule+@@iterator"></a>

### schedule.@@iterator() ⇒ [<code>Iterator.&lt;ScheduledTask&gt;</code>](#ScheduledTask)
<p>An iterator yielding all the tasks.</p>

**Kind**: instance method of [<code>Schedule</code>](#Schedule)  
<a name="ScheduledTask"></a>

## ScheduledTask
<p>A scheduled task, used for creating tasks.</p>

**Kind**: global class  

* [ScheduledTask](#ScheduledTask)
    * [.client](#ScheduledTask+client) : [<code>InlustrisClient</code>](#InlustrisClient)
    * [.taskName](#ScheduledTask+taskName) : <code>string</code>
    * [.recurring](#ScheduledTask+recurring) : [<code>Cron</code>](#Cron)
    * [.time](#ScheduledTask+time) : <code>Date</code>
    * [.id](#ScheduledTask+id) : <code>string</code>
    * [.data](#ScheduledTask+data) : <code>any</code>
    * [.task](#ScheduledTask+task) : [<code>Task</code>](#Task)
    * [.registry](#ScheduledTask+registry) : [<code>Schedule</code>](#Schedule)
    * [.run()](#ScheduledTask+run) ⇒ [<code>Promise.&lt;ScheduledTask&gt;</code>](#ScheduledTask)
    * [.update([options])](#ScheduledTask+update) ⇒ [<code>Promise.&lt;ScheduledTask&gt;</code>](#ScheduledTask)
    * [.delete()](#ScheduledTask+delete) ⇒ [<code>Promise.&lt;Schedule&gt;</code>](#Schedule)

<a name="ScheduledTask+client"></a>

### scheduledTask.client : [<code>InlustrisClient</code>](#InlustrisClient)
<p>The client</p>

**Kind**: instance property of [<code>ScheduledTask</code>](#ScheduledTask)  
**Read only**: true  
<a name="ScheduledTask+taskName"></a>

### scheduledTask.taskName : <code>string</code>
<p>The name of the task</p>

**Kind**: instance property of [<code>ScheduledTask</code>](#ScheduledTask)  
<a name="ScheduledTask+recurring"></a>

### scheduledTask.recurring : [<code>Cron</code>](#Cron)
<p>When the task should recur</p>

**Kind**: instance property of [<code>ScheduledTask</code>](#ScheduledTask)  
<a name="ScheduledTask+time"></a>

### scheduledTask.time : <code>Date</code>
<p>The time that this task should run</p>

**Kind**: instance property of [<code>ScheduledTask</code>](#ScheduledTask)  
<a name="ScheduledTask+id"></a>

### scheduledTask.id : <code>string</code>
<p>The unique ID of the task</p>

**Kind**: instance property of [<code>ScheduledTask</code>](#ScheduledTask)  
<a name="ScheduledTask+data"></a>

### scheduledTask.data : <code>any</code>
<p>The data to pass to the task when ran</p>

**Kind**: instance property of [<code>ScheduledTask</code>](#ScheduledTask)  
<a name="ScheduledTask+task"></a>

### scheduledTask.task : [<code>Task</code>](#Task)
<p>The task that this is for</p>

**Kind**: instance property of [<code>ScheduledTask</code>](#ScheduledTask)  
**Read only**: true  
<a name="ScheduledTask+registry"></a>

### scheduledTask.registry : [<code>Schedule</code>](#Schedule)
<p>The schedule for the task</p>

**Kind**: instance property of [<code>ScheduledTask</code>](#ScheduledTask)  
**Read only**: true  
<a name="ScheduledTask+run"></a>

### scheduledTask.run() ⇒ [<code>Promise.&lt;ScheduledTask&gt;</code>](#ScheduledTask)
<p>Runs the task, passing data to the appropriate task</p>

**Kind**: instance method of [<code>ScheduledTask</code>](#ScheduledTask)  
<a name="ScheduledTask+update"></a>

### scheduledTask.update([options]) ⇒ [<code>Promise.&lt;ScheduledTask&gt;</code>](#ScheduledTask)
<p>Updates a task, called if a task is recurring.</p>

**Kind**: instance method of [<code>ScheduledTask</code>](#ScheduledTask)  

| Param | Type | Description |
| --- | --- | --- |
| [options] | <code>ScheduledTaskUpdateOptions</code> | <p>The options to update the task with</p> |

<a name="ScheduledTask+delete"></a>

### scheduledTask.delete() ⇒ [<code>Promise.&lt;Schedule&gt;</code>](#Schedule)
<p>Deletes the task from the schedule.</p>

**Kind**: instance method of [<code>ScheduledTask</code>](#ScheduledTask)  
<a name="Base"></a>

## *Base*
<p>The base class for all pieces.</p>

**Kind**: global abstract class  

* *[Base](#Base)*
    * *[new Base(client, [options])](#new_Base_new)*
    * *[.client](#Base+client) : [<code>InlustrisClient</code>](#InlustrisClient)*
    * *[.options](#Base+options) : [<code>BaseOptions</code>](#BaseOptions)*
    * *[.registry](#Base+registry) : <code>BaseStore</code>*
    * *[.id](#Base+id) : <code>string</code>*
    * *[.enabled](#Base+enabled) : <code>boolean</code>*
    * *[.enable()](#Base+enable) ⇒ [<code>Base</code>](#Base)*
    * *[.disable()](#Base+disable) ⇒ [<code>Base</code>](#Base)*
    * *[.unload()](#Base+unload) ⇒ <code>void</code>*

<a name="new_Base_new"></a>

### *new Base(client, [options])*
<p>Initializes a new Base.</p>


| Param | Type | Default | Description |
| --- | --- | --- | --- |
| client | [<code>InlustrisClient</code>](#InlustrisClient) |  | <p>The Client for the Base</p> |
| [options] | [<code>BaseOptions</code>](#BaseOptions) | <code>{id:&#x27;&#x27;}</code> | <p>The base options</p> |

<a name="Base+client"></a>

### *base.client : [<code>InlustrisClient</code>](#InlustrisClient)*
<p>The client that initialized this base</p>

**Kind**: instance property of [<code>Base</code>](#Base)  
**Read only**: true  
<a name="Base+options"></a>

### *base.options : [<code>BaseOptions</code>](#BaseOptions)*
<p>The options for this base</p>

**Kind**: instance property of [<code>Base</code>](#Base)  
**Read only**: true  
<a name="Base+registry"></a>

### *base.registry : <code>BaseStore</code>*
<p>The Registry that holds this base</p>

**Kind**: instance property of [<code>Base</code>](#Base)  
**Read only**: true  
<a name="Base+id"></a>

### *base.id : <code>string</code>*
<p>The ID of this base</p>

**Kind**: instance property of [<code>Base</code>](#Base)  
**Read only**: true  
<a name="Base+enabled"></a>

### *base.enabled : <code>boolean</code>*
<p>Whether this base is enabled</p>

**Kind**: instance property of [<code>Base</code>](#Base)  
<a name="Base+enable"></a>

### *base.enable() ⇒ [<code>Base</code>](#Base)*
<p>Enables the base. Shortcut for <code>&lt;base&gt;.enabled = true</code>.</p>

**Kind**: instance method of [<code>Base</code>](#Base)  
**Chainable**  
**Emits**: [<code>baseEnabled</code>](#InlustrisClient+event_baseEnabled)  
<a name="Base+disable"></a>

### *base.disable() ⇒ [<code>Base</code>](#Base)*
<p>Disables the base. Shortcut for <code>&lt;base&gt;.enabled = false</code>.</p>

**Kind**: instance method of [<code>Base</code>](#Base)  
**Chainable**  
**Emits**: [<code>baseDisabled</code>](#InlustrisClient+event_baseDisabled)  
<a name="Base+unload"></a>

### *base.unload() ⇒ <code>void</code>*
<p>Unloads the base, and deletes it from the registry.</p>

**Kind**: instance method of [<code>Base</code>](#Base)  
**Emits**: [<code>baseUnloaded</code>](#InlustrisClient+event_baseUnloaded)  
<a name="Command"></a>

## Command ⇐ [<code>Base</code>](#Base)
<p>Command class for creating commands.</p>

**Kind**: global class  
**Extends**: [<code>Base</code>](#Base)  

* [Command](#Command) ⇐ [<code>Base</code>](#Base)
    * [.separator](#Command+separator) : <code>string</code>
    * [.client](#Base+client) : [<code>InlustrisClient</code>](#InlustrisClient)
    * [.options](#Base+options) : [<code>BaseOptions</code>](#BaseOptions)
    * [.registry](#Base+registry) : <code>BaseStore</code>
    * [.id](#Base+id) : <code>string</code>
    * [.enabled](#Base+enabled) : <code>boolean</code>
    * *[.args()](#Command+args)*
    * [.enable()](#Base+enable) ⇒ [<code>Base</code>](#Base)
    * [.disable()](#Base+disable) ⇒ [<code>Base</code>](#Base)
    * [.unload()](#Base+unload) ⇒ <code>void</code>

<a name="Command+separator"></a>

### command.separator : <code>string</code>
<p>The separator for argument generators</p>

**Kind**: instance property of [<code>Command</code>](#Command)  
<a name="Base+client"></a>

### command.client : [<code>InlustrisClient</code>](#InlustrisClient)
<p>The client that initialized this base</p>

**Kind**: instance property of [<code>Command</code>](#Command)  
**Overrides**: [<code>client</code>](#Base+client)  
**Read only**: true  
<a name="Base+options"></a>

### command.options : [<code>BaseOptions</code>](#BaseOptions)
<p>The options for this base</p>

**Kind**: instance property of [<code>Command</code>](#Command)  
**Overrides**: [<code>options</code>](#Base+options)  
**Read only**: true  
<a name="Base+registry"></a>

### command.registry : <code>BaseStore</code>
<p>The Registry that holds this base</p>

**Kind**: instance property of [<code>Command</code>](#Command)  
**Overrides**: [<code>registry</code>](#Base+registry)  
**Read only**: true  
<a name="Base+id"></a>

### command.id : <code>string</code>
<p>The ID of this base</p>

**Kind**: instance property of [<code>Command</code>](#Command)  
**Overrides**: [<code>id</code>](#Base+id)  
**Read only**: true  
<a name="Base+enabled"></a>

### command.enabled : <code>boolean</code>
<p>Whether this base is enabled</p>

**Kind**: instance property of [<code>Command</code>](#Command)  
**Overrides**: [<code>enabled</code>](#Base+enabled)  
<a name="Command+args"></a>

### *command.args()*
<p>Abstract argument generator, needs to be used if arguments are needed with commands.</p>

**Kind**: instance abstract method of [<code>Command</code>](#Command)  
<a name="Base+enable"></a>

### command.enable() ⇒ [<code>Base</code>](#Base)
<p>Enables the base. Shortcut for <code>&lt;base&gt;.enabled = true</code>.</p>

**Kind**: instance method of [<code>Command</code>](#Command)  
**Chainable**  
**Overrides**: [<code>enable</code>](#Base+enable)  
**Emits**: [<code>baseEnabled</code>](#InlustrisClient+event_baseEnabled)  
<a name="Base+disable"></a>

### command.disable() ⇒ [<code>Base</code>](#Base)
<p>Disables the base. Shortcut for <code>&lt;base&gt;.enabled = false</code>.</p>

**Kind**: instance method of [<code>Command</code>](#Command)  
**Chainable**  
**Overrides**: [<code>disable</code>](#Base+disable)  
**Emits**: [<code>baseDisabled</code>](#InlustrisClient+event_baseDisabled)  
<a name="Base+unload"></a>

### command.unload() ⇒ <code>void</code>
<p>Unloads the base, and deletes it from the registry.</p>

**Kind**: instance method of [<code>Command</code>](#Command)  
**Overrides**: [<code>unload</code>](#Base+unload)  
**Emits**: [<code>baseUnloaded</code>](#InlustrisClient+event_baseUnloaded)  
<a name="Event"></a>

## Event ⇐ [<code>Base</code>](#Base)
<p>The event class for creating events.</p>

**Kind**: global class  
**Extends**: [<code>Base</code>](#Base)  

* [Event](#Event) ⇐ [<code>Base</code>](#Base)
    * [.event](#Event+event) : <code>string</code>
    * [.once](#Event+once) : <code>boolean</code>
    * [.client](#Base+client) : [<code>InlustrisClient</code>](#InlustrisClient)
    * [.options](#Base+options) : [<code>BaseOptions</code>](#BaseOptions)
    * [.registry](#Base+registry) : <code>BaseStore</code>
    * [.id](#Base+id) : <code>string</code>
    * [.enabled](#Base+enabled) : <code>boolean</code>
    * [.enable()](#Event+enable) ⇒ [<code>Event</code>](#Event)
    * [.disable()](#Event+disable) ⇒ [<code>Event</code>](#Event)
    * [.unload()](#Base+unload) ⇒ <code>void</code>

<a name="Event+event"></a>

### event.event : <code>string</code>
<p>The event this base listens to</p>

**Kind**: instance property of [<code>Event</code>](#Event)  
**Read only**: true  
<a name="Event+once"></a>

### event.once : <code>boolean</code>
<p>Whether this event is emitted once or not</p>

**Kind**: instance property of [<code>Event</code>](#Event)  
**Read only**: true  
<a name="Base+client"></a>

### event.client : [<code>InlustrisClient</code>](#InlustrisClient)
<p>The client that initialized this base</p>

**Kind**: instance property of [<code>Event</code>](#Event)  
**Overrides**: [<code>client</code>](#Base+client)  
**Read only**: true  
<a name="Base+options"></a>

### event.options : [<code>BaseOptions</code>](#BaseOptions)
<p>The options for this base</p>

**Kind**: instance property of [<code>Event</code>](#Event)  
**Overrides**: [<code>options</code>](#Base+options)  
**Read only**: true  
<a name="Base+registry"></a>

### event.registry : <code>BaseStore</code>
<p>The Registry that holds this base</p>

**Kind**: instance property of [<code>Event</code>](#Event)  
**Overrides**: [<code>registry</code>](#Base+registry)  
**Read only**: true  
<a name="Base+id"></a>

### event.id : <code>string</code>
<p>The ID of this base</p>

**Kind**: instance property of [<code>Event</code>](#Event)  
**Overrides**: [<code>id</code>](#Base+id)  
**Read only**: true  
<a name="Base+enabled"></a>

### event.enabled : <code>boolean</code>
<p>Whether this base is enabled</p>

**Kind**: instance property of [<code>Event</code>](#Event)  
**Overrides**: [<code>enabled</code>](#Base+enabled)  
<a name="Event+enable"></a>

### event.enable() ⇒ [<code>Event</code>](#Event)
<p>Enables the event, and adds the listener to the event emitter.</p>

**Kind**: instance method of [<code>Event</code>](#Event)  
**Chainable**  
**Overrides**: [<code>enable</code>](#Base+enable)  
**Emits**: [<code>baseEnabled</code>](#InlustrisClient+event_baseEnabled)  
<a name="Event+disable"></a>

### event.disable() ⇒ [<code>Event</code>](#Event)
<p>Disables the event, and removes the listener from the event emitter.</p>

**Kind**: instance method of [<code>Event</code>](#Event)  
**Chainable**  
**Overrides**: [<code>disable</code>](#Base+disable)  
**Emits**: [<code>baseDisabled</code>](#InlustrisClient+event_baseDisabled)  
<a name="Base+unload"></a>

### event.unload() ⇒ <code>void</code>
<p>Unloads the base, and deletes it from the registry.</p>

**Kind**: instance method of [<code>Event</code>](#Event)  
**Overrides**: [<code>unload</code>](#Base+unload)  
**Emits**: [<code>baseUnloaded</code>](#InlustrisClient+event_baseUnloaded)  
<a name="Task"></a>

## *Task ⇐ [<code>Base</code>](#Base)*
<p>The task class, used for creating tasks.</p>

**Kind**: global abstract class  
**Extends**: [<code>Base</code>](#Base)  

* *[Task](#Task) ⇐ [<code>Base</code>](#Base)*
    * *[.client](#Base+client) : [<code>InlustrisClient</code>](#InlustrisClient)*
    * *[.options](#Base+options) : [<code>BaseOptions</code>](#BaseOptions)*
    * *[.registry](#Base+registry) : <code>BaseStore</code>*
    * *[.id](#Base+id) : <code>string</code>*
    * *[.enabled](#Base+enabled) : <code>boolean</code>*
    * *[.enable()](#Base+enable) ⇒ [<code>Base</code>](#Base)*
    * *[.disable()](#Base+disable) ⇒ [<code>Base</code>](#Base)*
    * *[.unload()](#Base+unload) ⇒ <code>void</code>*

<a name="Base+client"></a>

### *task.client : [<code>InlustrisClient</code>](#InlustrisClient)*
<p>The client that initialized this base</p>

**Kind**: instance property of [<code>Task</code>](#Task)  
**Read only**: true  
<a name="Base+options"></a>

### *task.options : [<code>BaseOptions</code>](#BaseOptions)*
<p>The options for this base</p>

**Kind**: instance property of [<code>Task</code>](#Task)  
**Read only**: true  
<a name="Base+registry"></a>

### *task.registry : <code>BaseStore</code>*
<p>The Registry that holds this base</p>

**Kind**: instance property of [<code>Task</code>](#Task)  
**Read only**: true  
<a name="Base+id"></a>

### *task.id : <code>string</code>*
<p>The ID of this base</p>

**Kind**: instance property of [<code>Task</code>](#Task)  
**Read only**: true  
<a name="Base+enabled"></a>

### *task.enabled : <code>boolean</code>*
<p>Whether this base is enabled</p>

**Kind**: instance property of [<code>Task</code>](#Task)  
<a name="Base+enable"></a>

### *task.enable() ⇒ [<code>Base</code>](#Base)*
<p>Enables the base. Shortcut for <code>&lt;base&gt;.enabled = true</code>.</p>

**Kind**: instance method of [<code>Task</code>](#Task)  
**Chainable**  
**Emits**: [<code>baseEnabled</code>](#InlustrisClient+event_baseEnabled)  
<a name="Base+disable"></a>

### *task.disable() ⇒ [<code>Base</code>](#Base)*
<p>Disables the base. Shortcut for <code>&lt;base&gt;.enabled = false</code>.</p>

**Kind**: instance method of [<code>Task</code>](#Task)  
**Chainable**  
**Emits**: [<code>baseDisabled</code>](#InlustrisClient+event_baseDisabled)  
<a name="Base+unload"></a>

### *task.unload() ⇒ <code>void</code>*
<p>Unloads the base, and deletes it from the registry.</p>

**Kind**: instance method of [<code>Task</code>](#Task)  
**Emits**: [<code>baseUnloaded</code>](#InlustrisClient+event_baseUnloaded)  
<a name="ClientUtil"></a>

## ClientUtil
<p>Utility methods to use for common tasks.</p>

**Kind**: global class  

* [ClientUtil](#ClientUtil)
    * [.resolveUser(text, users, [caseSensitive], [wholeWord])](#ClientUtil+resolveUser) ⇒ [<code>User</code>](https://discord.js.org/#/docs/main/master/class/User)
    * [.resolveUsers(text, users, [caseSensitive], [wholeWord])](#ClientUtil+resolveUsers) ⇒ <code>Collection.&lt;Snowflake, User&gt;</code>
    * [.checkUser(text, user, [caseSensitive], [wholeWord])](#ClientUtil+checkUser) ⇒ <code>boolean</code>
    * [.resolveMember(text, members, [caseSensitive], [wholeWord])](#ClientUtil+resolveMember) ⇒ [<code>GuildMember</code>](https://discord.js.org/#/docs/main/master/class/GuildMember)
    * [.resolveMembers(text, members, [caseSensitive], [wholeWord])](#ClientUtil+resolveMembers) ⇒ <code>Collection.&lt;Snowflake, GuildMember&gt;</code>
    * [.checkMember(text, member, [caseSensitive], [wholeWord])](#ClientUtil+checkMember) ⇒ <code>boolean</code>
    * [.resolveChannel(text, channels, [caseSensitive], [wholeWord])](#ClientUtil+resolveChannel) ⇒ [<code>GuildChannel</code>](https://discord.js.org/#/docs/main/master/class/GuildChannel)
    * [.resolveChannels(text, channels, [caseSensitive], [wholeWord])](#ClientUtil+resolveChannels) ⇒ <code>Collection.&lt;Snowflake, GuildChannel&gt;</code>
    * [.checkChannel(text, channel, [caseSensitive], [wholeWord])](#ClientUtil+checkChannel) ⇒ <code>boolean</code>
    * [.resolveRole(text, roles, [caseSensitive], [wholeWord])](#ClientUtil+resolveRole) ⇒ <code>Role</code>
    * [.resolveRoles(text, roles, [caseSensitive], [wholeWord])](#ClientUtil+resolveRoles) ⇒ <code>Collection.&lt;Snowflake, Role&gt;</code>
    * [.checkRole(text, role, [caseSensitive], [wholeWord])](#ClientUtil+checkRole) ⇒ <code>boolean</code>
    * [.resolveEmoji(text, emojis, [caseSensitive], [wholeWord])](#ClientUtil+resolveEmoji) ⇒ [<code>Emoji</code>](https://discord.js.org/#/docs/main/master/class/Emoji)
    * [.resolveEmojis(text, emojis, [caseSensitive], [wholeWord])](#ClientUtil+resolveEmojis) ⇒ <code>Collection.&lt;Snowflake, Emoji&gt;</code>
    * [.checkEmoji(text, emoji, [caseSensitive], [wholeWord])](#ClientUtil+checkEmoji) ⇒ <code>boolean</code>
    * [.resolveGuild(text, guilds, [caseSensitive], [wholeWord])](#ClientUtil+resolveGuild) ⇒ [<code>Guild</code>](https://discord.js.org/#/docs/main/master/class/Guild)
    * [.resolveGuilds(text, guilds, [caseSensitive], [wholeWord])](#ClientUtil+resolveGuilds) ⇒ <code>Collection.&lt;Snowflake, Guild&gt;</code>
    * [.checkGuild(text, guild, [caseSensitive], [wholeWord])](#ClientUtil+checkGuild) ⇒ <code>boolean</code>
    * [.permissionNames()](#ClientUtil+permissionNames) ⇒ <code>Array.&lt;string&gt;</code>
    * [.resolvePermissionNumber(num)](#ClientUtil+resolvePermissionNumber) ⇒ <code>Array.&lt;string&gt;</code>
    * [.compareStreaming(oldMember, newMember)](#ClientUtil+compareStreaming) ⇒ <code>number</code>
    * [.fetchMember(guild, id, cache)](#ClientUtil+fetchMember) ⇒ [<code>Promise.&lt;GuildMember&gt;</code>](https://discord.js.org/#/docs/main/master/class/GuildMember)
    * [.embed([data])](#ClientUtil+embed) ⇒ [<code>MessageEmbed</code>](https://discord.js.org/#/docs/main/master/class/MessageEmbed)
    * [.attachment(file, [name])](#ClientUtil+attachment) ⇒ [<code>MessageAttachment</code>](https://discord.js.org/#/docs/main/master/class/MessageAttachment)
    * [.collection([iterable])](#ClientUtil+collection) ⇒ [<code>Collection</code>](https://discord.js.org/#/docs/main/master/class/Collection)
    * [.list([iterable])](#ClientUtil+list) ⇒ [<code>List</code>](#List)

<a name="ClientUtil+resolveUser"></a>

### clientUtil.resolveUser(text, users, [caseSensitive], [wholeWord]) ⇒ [<code>User</code>](https://discord.js.org/#/docs/main/master/class/User)
<p>Resolves a user from a string, such as an ID, a name, or a mention.</p>

**Kind**: instance method of [<code>ClientUtil</code>](#ClientUtil)  

| Param | Type | Default | Description |
| --- | --- | --- | --- |
| text | <code>string</code> |  | <p>Text to resolve</p> |
| users | <code>Collection.&lt;Snowflake, User&gt;</code> |  | <p>Collection of users to find in</p> |
| [caseSensitive] | <code>boolean</code> | <code>false</code> | <p>Makes finding by name case sensitive</p> |
| [wholeWord] | <code>boolean</code> | <code>false</code> | <p>Makes finding by name match whole word only</p> |

<a name="ClientUtil+resolveUsers"></a>

### clientUtil.resolveUsers(text, users, [caseSensitive], [wholeWord]) ⇒ <code>Collection.&lt;Snowflake, User&gt;</code>
<p>Resolves multiple users from a string, such as an ID, a name, or a mention.</p>

**Kind**: instance method of [<code>ClientUtil</code>](#ClientUtil)  

| Param | Type | Default | Description |
| --- | --- | --- | --- |
| text | <code>string</code> |  | <p>Text to resolve</p> |
| users | <code>Collection.&lt;Snowflake, User&gt;</code> |  | <p>Collection of users to find in</p> |
| [caseSensitive] | <code>boolean</code> | <code>false</code> | <p>Makes finding by name case sensitive</p> |
| [wholeWord] | <code>boolean</code> | <code>false</code> | <p>Makes finding by name match whole word only</p> |

<a name="ClientUtil+checkUser"></a>

### clientUtil.checkUser(text, user, [caseSensitive], [wholeWord]) ⇒ <code>boolean</code>
<p>Checks if a string could be referring to a user.</p>

**Kind**: instance method of [<code>ClientUtil</code>](#ClientUtil)  

| Param | Type | Default | Description |
| --- | --- | --- | --- |
| text | <code>string</code> |  | <p>Text to check</p> |
| user | [<code>User</code>](https://discord.js.org/#/docs/main/master/class/User) |  | <p>User to check</p> |
| [caseSensitive] | <code>boolean</code> | <code>false</code> | <p>Makes checking by name case sensitive</p> |
| [wholeWord] | <code>boolean</code> | <code>false</code> | <p>Makes checking by name match whole word only</p> |

<a name="ClientUtil+resolveMember"></a>

### clientUtil.resolveMember(text, members, [caseSensitive], [wholeWord]) ⇒ [<code>GuildMember</code>](https://discord.js.org/#/docs/main/master/class/GuildMember)
<p>Resolves a member from a string, such as an ID, a name, or a mention.</p>

**Kind**: instance method of [<code>ClientUtil</code>](#ClientUtil)  

| Param | Type | Default | Description |
| --- | --- | --- | --- |
| text | <code>string</code> |  | <p>Text to resolve</p> |
| members | <code>Collection.&lt;Snowflake, GuildMember&gt;</code> |  | <p>Collection of members to find in</p> |
| [caseSensitive] | <code>boolean</code> | <code>false</code> | <p>Makes finding by name case sensitive</p> |
| [wholeWord] | <code>boolean</code> | <code>false</code> | <p>Makes finding by name match whole word only</p> |

<a name="ClientUtil+resolveMembers"></a>

### clientUtil.resolveMembers(text, members, [caseSensitive], [wholeWord]) ⇒ <code>Collection.&lt;Snowflake, GuildMember&gt;</code>
<p>Resolves multiple members from a string, such as an ID, a name, or a mention.</p>

**Kind**: instance method of [<code>ClientUtil</code>](#ClientUtil)  

| Param | Type | Default | Description |
| --- | --- | --- | --- |
| text | <code>string</code> |  | <p>Text to resolve</p> |
| members | <code>Collection.&lt;Snowflake, GuildMember&gt;</code> |  | <p>Collection of members to find in</p> |
| [caseSensitive] | <code>boolean</code> | <code>false</code> | <p>Makes finding by name case sensitive</p> |
| [wholeWord] | <code>boolean</code> | <code>false</code> | <p>Makes finding by name match whole word only</p> |

<a name="ClientUtil+checkMember"></a>

### clientUtil.checkMember(text, member, [caseSensitive], [wholeWord]) ⇒ <code>boolean</code>
<p>Checks if a string could be referring to a member.</p>

**Kind**: instance method of [<code>ClientUtil</code>](#ClientUtil)  

| Param | Type | Default | Description |
| --- | --- | --- | --- |
| text | <code>string</code> |  | <p>Text to check</p> |
| member | [<code>GuildMember</code>](https://discord.js.org/#/docs/main/master/class/GuildMember) |  | <p>Member to check</p> |
| [caseSensitive] | <code>boolean</code> | <code>false</code> | <p>Makes checking by name case sensitive</p> |
| [wholeWord] | <code>boolean</code> | <code>false</code> | <p>Makes checking by name match whole word only</p> |

<a name="ClientUtil+resolveChannel"></a>

### clientUtil.resolveChannel(text, channels, [caseSensitive], [wholeWord]) ⇒ [<code>GuildChannel</code>](https://discord.js.org/#/docs/main/master/class/GuildChannel)
<p>Resolves a channel from a string, such as ID, a name, or a mention.</p>

**Kind**: instance method of [<code>ClientUtil</code>](#ClientUtil)  

| Param | Type | Default | Description |
| --- | --- | --- | --- |
| text | <code>string</code> |  | <p>Text to resolve</p> |
| channels | <code>Collection.&lt;Snowflake, GuildChannel&gt;</code> |  | <p>Collection of channels to find in</p> |
| [caseSensitive] | <code>boolean</code> | <code>false</code> | <p>Makes finding by name case sensitive</p> |
| [wholeWord] | <code>boolean</code> | <code>false</code> | <p>Makes finding by name match whole word only</p> |

<a name="ClientUtil+resolveChannels"></a>

### clientUtil.resolveChannels(text, channels, [caseSensitive], [wholeWord]) ⇒ <code>Collection.&lt;Snowflake, GuildChannel&gt;</code>
<p>Resolves multiple channels from a string, such as an ID, a name, or a mention.</p>

**Kind**: instance method of [<code>ClientUtil</code>](#ClientUtil)  

| Param | Type | Default | Description |
| --- | --- | --- | --- |
| text | <code>string</code> |  | <p>Text to resolve</p> |
| channels | <code>Collection.&lt;Snowflake, GuildChannel&gt;</code> |  | <p>Collection of channels to find in</p> |
| [caseSensitive] | <code>boolean</code> | <code>false</code> | <p>Makes finding by name case sensitive</p> |
| [wholeWord] | <code>boolean</code> | <code>false</code> | <p>Makes finding by name match whole word only</p> |

<a name="ClientUtil+checkChannel"></a>

### clientUtil.checkChannel(text, channel, [caseSensitive], [wholeWord]) ⇒ <code>boolean</code>
<p>Checks if a string could be referring to a channel.</p>

**Kind**: instance method of [<code>ClientUtil</code>](#ClientUtil)  

| Param | Type | Default | Description |
| --- | --- | --- | --- |
| text | <code>string</code> |  | <p>Text to check</p> |
| channel | [<code>GuildChannel</code>](https://discord.js.org/#/docs/main/master/class/GuildChannel) |  | <p>Channel to check</p> |
| [caseSensitive] | <code>boolean</code> | <code>false</code> | <p>Makes checking by name case sensitive</p> |
| [wholeWord] | <code>boolean</code> | <code>false</code> | <p>Makes checking by name match whole word only</p> |

<a name="ClientUtil+resolveRole"></a>

### clientUtil.resolveRole(text, roles, [caseSensitive], [wholeWord]) ⇒ <code>Role</code>
<p>Resolves a role from a string, such as an ID, a name, or a mention.</p>

**Kind**: instance method of [<code>ClientUtil</code>](#ClientUtil)  

| Param | Type | Default | Description |
| --- | --- | --- | --- |
| text | <code>string</code> |  | <p>Text to resolve</p> |
| roles | <code>Collection.&lt;Snowflake, Role&gt;</code> |  | <p>Collection of roles to find in</p> |
| [caseSensitive] | <code>boolean</code> | <code>false</code> | <p>Makes finding by name case sensitive</p> |
| [wholeWord] | <code>boolean</code> | <code>false</code> | <p>Makes finding by name match whole word only</p> |

<a name="ClientUtil+resolveRoles"></a>

### clientUtil.resolveRoles(text, roles, [caseSensitive], [wholeWord]) ⇒ <code>Collection.&lt;Snowflake, Role&gt;</code>
<p>Resolves multiple roles from a string, such as an ID, a name, or a mention.</p>

**Kind**: instance method of [<code>ClientUtil</code>](#ClientUtil)  

| Param | Type | Default | Description |
| --- | --- | --- | --- |
| text | <code>string</code> |  | <p>Text to resolve</p> |
| roles | <code>Collection.&lt;Snowflake, Role&gt;</code> |  | <p>Collection of roles to find in</p> |
| [caseSensitive] | <code>boolean</code> | <code>false</code> | <p>Makes finding by name case sensitive</p> |
| [wholeWord] | <code>boolean</code> | <code>false</code> | <p>Makes finding by name match whole word only</p> |

<a name="ClientUtil+checkRole"></a>

### clientUtil.checkRole(text, role, [caseSensitive], [wholeWord]) ⇒ <code>boolean</code>
<p>Checks if a string could be referring to a role.</p>

**Kind**: instance method of [<code>ClientUtil</code>](#ClientUtil)  

| Param | Type | Default | Description |
| --- | --- | --- | --- |
| text | <code>string</code> |  | <p>Text to check</p> |
| role | [<code>Role</code>](https://discord.js.org/#/docs/main/master/class/Role) |  | <p>Role to check</p> |
| [caseSensitive] | <code>boolean</code> | <code>false</code> | <p>Makes checking by name case sensitive</p> |
| [wholeWord] | <code>boolean</code> | <code>false</code> | <p>Makes checking by name match full word only</p> |

<a name="ClientUtil+resolveEmoji"></a>

### clientUtil.resolveEmoji(text, emojis, [caseSensitive], [wholeWord]) ⇒ [<code>Emoji</code>](https://discord.js.org/#/docs/main/master/class/Emoji)
<p>Resolves a custom emoji from a string, such as a name or a mention.</p>

**Kind**: instance method of [<code>ClientUtil</code>](#ClientUtil)  

| Param | Type | Default | Description |
| --- | --- | --- | --- |
| text | <code>string</code> |  | <p>Text to resolve</p> |
| emojis | <code>Collection.&lt;Snowflake, Emoji&gt;</code> |  | <p>Collection of emojis to find in</p> |
| [caseSensitive] | <code>boolean</code> | <code>false</code> | <p>Makes finding by name case sensitive</p> |
| [wholeWord] | <code>boolean</code> | <code>false</code> | <p>Makes finding by name match whole word only</p> |

<a name="ClientUtil+resolveEmojis"></a>

### clientUtil.resolveEmojis(text, emojis, [caseSensitive], [wholeWord]) ⇒ <code>Collection.&lt;Snowflake, Emoji&gt;</code>
<p>Resolves multiple custom emojis from a string, such as a name or a mention.</p>

**Kind**: instance method of [<code>ClientUtil</code>](#ClientUtil)  

| Param | Type | Default | Description |
| --- | --- | --- | --- |
| text | <code>string</code> |  | <p>Text to resolve</p> |
| emojis | <code>Collection.&lt;Snowflake, Emoji&gt;</code> |  | <p>Collection of emojis to find in</p> |
| [caseSensitive] | <code>boolean</code> | <code>false</code> | <p>Makes finding by name case sensitive</p> |
| [wholeWord] | <code>boolean</code> | <code>false</code> | <p>Makes finding by name match whole word only</p> |

<a name="ClientUtil+checkEmoji"></a>

### clientUtil.checkEmoji(text, emoji, [caseSensitive], [wholeWord]) ⇒ <code>boolean</code>
<p>Checks if a string could be referring to an emoji.</p>

**Kind**: instance method of [<code>ClientUtil</code>](#ClientUtil)  

| Param | Type | Default | Description |
| --- | --- | --- | --- |
| text | <code>string</code> |  | <p>Text to check</p> |
| emoji | [<code>Emoji</code>](https://discord.js.org/#/docs/main/master/class/Emoji) |  | <p>Emoji to check</p> |
| [caseSensitive] | <code>boolean</code> | <code>false</code> | <p>Makes checking by name case sensitive</p> |
| [wholeWord] | <code>boolean</code> | <code>false</code> | <p>Makes checking by name match whole word only</p> |

<a name="ClientUtil+resolveGuild"></a>

### clientUtil.resolveGuild(text, guilds, [caseSensitive], [wholeWord]) ⇒ [<code>Guild</code>](https://discord.js.org/#/docs/main/master/class/Guild)
<p>Resolves a guild from a string, such as an ID or name.</p>

**Kind**: instance method of [<code>ClientUtil</code>](#ClientUtil)  

| Param | Type | Default | Description |
| --- | --- | --- | --- |
| text | <code>string</code> |  | <p>Text to resolve</p> |
| guilds | <code>Collection.&lt;Snowflake, Guild&gt;</code> |  | <p>Collection of guilds to find in</p> |
| [caseSensitive] | <code>boolean</code> | <code>false</code> | <p>Makes finding by name case sensitive</p> |
| [wholeWord] | <code>boolean</code> | <code>false</code> | <p>Makes finding by name full word only</p> |

<a name="ClientUtil+resolveGuilds"></a>

### clientUtil.resolveGuilds(text, guilds, [caseSensitive], [wholeWord]) ⇒ <code>Collection.&lt;Snowflake, Guild&gt;</code>
<p>Resolves multiple guilds from a string, such as an ID or name.</p>

**Kind**: instance method of [<code>ClientUtil</code>](#ClientUtil)  

| Param | Type | Default | Description |
| --- | --- | --- | --- |
| text | <code>string</code> |  | <p>Text to resolve</p> |
| guilds | <code>Collection.&lt;Snowflake, Guild&gt;</code> |  | <p>Collection of guilds to find in</p> |
| [caseSensitive] | <code>boolean</code> | <code>false</code> | <p>Makes finding by name case sensitive</p> |
| [wholeWord] | <code>boolean</code> | <code>false</code> | <p>Makes finding by name full word only</p> |

<a name="ClientUtil+checkGuild"></a>

### clientUtil.checkGuild(text, guild, [caseSensitive], [wholeWord]) ⇒ <code>boolean</code>
<p>Checks if a string could be referring to a guild.</p>

**Kind**: instance method of [<code>ClientUtil</code>](#ClientUtil)  

| Param | Type | Default | Description |
| --- | --- | --- | --- |
| text | <code>string</code> |  | <p>Text to check</p> |
| guild | [<code>Guild</code>](https://discord.js.org/#/docs/main/master/class/Guild) |  | <p>Guild to check</p> |
| [caseSensitive] | <code>boolean</code> | <code>false</code> | <p>Makes checking by name case sensitive</p> |
| [wholeWord] | <code>boolean</code> | <code>false</code> | <p>Makes checking by name match full word only</p> |

<a name="ClientUtil+permissionNames"></a>

### clientUtil.permissionNames() ⇒ <code>Array.&lt;string&gt;</code>
<p>An array of permission names.</p>

**Kind**: instance method of [<code>ClientUtil</code>](#ClientUtil)  
<a name="ClientUtil+resolvePermissionNumber"></a>

### clientUtil.resolvePermissionNumber(num) ⇒ <code>Array.&lt;string&gt;</code>
<p>Resolved a permission number and returns an array of permissions names.</p>

**Kind**: instance method of [<code>ClientUtil</code>](#ClientUtil)  

| Param | Type | Description |
| --- | --- | --- |
| num | <code>number</code> | <p>The permissions number</p> |

<a name="ClientUtil+compareStreaming"></a>

### clientUtil.compareStreaming(oldMember, newMember) ⇒ <code>number</code>
<p>Compares two member objects presences and checks if they stopped or started a stream or not.
Returns <code>0</code>, <code>1</code>, or <code>2</code> for no change, stopped, or started.</p>

**Kind**: instance method of [<code>ClientUtil</code>](#ClientUtil)  

| Param | Type | Description |
| --- | --- | --- |
| oldMember | [<code>GuildMember</code>](https://discord.js.org/#/docs/main/master/class/GuildMember) | <p>The old guild member</p> |
| newMember | [<code>GuildMember</code>](https://discord.js.org/#/docs/main/master/class/GuildMember) | <p>The new guild member</p> |

<a name="ClientUtil+fetchMember"></a>

### clientUtil.fetchMember(guild, id, cache) ⇒ [<code>Promise.&lt;GuildMember&gt;</code>](https://discord.js.org/#/docs/main/master/class/GuildMember)
<p>Combination of <code>&lt;Client&gt;.fetchUser()</code> and <code>&lt;Guild&gt;.fetchMember()</code>.</p>

**Kind**: instance method of [<code>ClientUtil</code>](#ClientUtil)  

| Param | Type | Description |
| --- | --- | --- |
| guild | [<code>Guild</code>](https://discord.js.org/#/docs/main/master/class/Guild) | <p>The guild to fetch in</p> |
| id | <code>string</code> | <p>ID of the user to fetch</p> |
| cache | <code>boolean</code> | <p>Whether or not to add to the cache</p> |

<a name="ClientUtil+embed"></a>

### clientUtil.embed([data]) ⇒ [<code>MessageEmbed</code>](https://discord.js.org/#/docs/main/master/class/MessageEmbed)
<p>Makes a MessageEmbed.</p>

**Kind**: instance method of [<code>ClientUtil</code>](#ClientUtil)  

| Param | Type | Description |
| --- | --- | --- |
| [data] | [<code>MessageEmbed</code>](https://discord.js.org/#/docs/main/master/class/MessageEmbed) \| [<code>MessageEmbedOptions</code>](https://discord.js.org/#/docs/main/master/typedef/MessageEmbedOptions) | <p>The data to use for the embed</p> |

<a name="ClientUtil+attachment"></a>

### clientUtil.attachment(file, [name]) ⇒ [<code>MessageAttachment</code>](https://discord.js.org/#/docs/main/master/class/MessageAttachment)
<p>Makes a MessageAttachment.</p>

**Kind**: instance method of [<code>ClientUtil</code>](#ClientUtil)  

| Param | Type | Description |
| --- | --- | --- |
| file | [<code>BufferResolvable</code>](https://discord.js.org/#/docs/main/master/typedef/BufferResolvable) \| <code>Stream</code> | <p>The file</p> |
| [name] | <code>string</code> | <p>The name of the file</p> |

<a name="ClientUtil+collection"></a>

### clientUtil.collection([iterable]) ⇒ [<code>Collection</code>](https://discord.js.org/#/docs/main/master/class/Collection)
<p>Makes a Collection.</p>

**Kind**: instance method of [<code>ClientUtil</code>](#ClientUtil)  

| Param | Type | Description |
| --- | --- | --- |
| [iterable] | <code>Iterable</code> | <p>Entries to fill with</p> |

<a name="ClientUtil+list"></a>

### clientUtil.list([iterable]) ⇒ [<code>List</code>](#List)
<p>Makes a List.</p>

**Kind**: instance method of [<code>ClientUtil</code>](#ClientUtil)  

| Param | Type | Description |
| --- | --- | --- |
| [iterable] | <code>Iterable</code> | <p>Entries to fill with</p> |

<a name="Cron"></a>

## Cron
<p>Cron utility class, used for creating tasks.</p>

**Kind**: global class  

* [Cron](#Cron)
    * [new Cron(cron)](#new_Cron_new)
    * [.cron](#Cron+cron) : <code>string</code>
    * [.normalized](#Cron+normalized) : <code>string</code>
    * [.next([outset], [origin])](#Cron+next) ⇒ <code>Date</code>

<a name="new_Cron_new"></a>

### new Cron(cron)

| Param | Type |
| --- | --- |
| cron | <code>string</code> | 

<a name="Cron+cron"></a>

### cron.cron : <code>string</code>
<p>The cron string that generated this</p>

**Kind**: instance property of [<code>Cron</code>](#Cron)  
<a name="Cron+normalized"></a>

### cron.normalized : <code>string</code>
<p>The normalized cron string</p>

**Kind**: instance property of [<code>Cron</code>](#Cron)  
<a name="Cron+next"></a>

### cron.next([outset], [origin]) ⇒ <code>Date</code>
<p>Gets the next instance that this will trigger.</p>

**Kind**: instance method of [<code>Cron</code>](#Cron)  

| Param | Type | Default | Description |
| --- | --- | --- | --- |
| [outset] | <code>Date</code> | <code>new Date()</code> | <p>The previous date</p> |
| [origin] | <code>boolean</code> | <code>true</code> | <p>Whether this is the original call</p> |

<a name="InlustrisError"></a>

## InlustrisError ⇐ <code>Error</code>
<p>An error class used to make error throwing universal.</p>

**Kind**: global class  
**Extends**: <code>Error</code>  
<a name="List"></a>

## List ⇐ <code>Set</code>
<p>A Set with additional utility methods.</p>

**Kind**: global class  
**Extends**: <code>Set</code>  

* [List](#List) ⇐ <code>Set</code>
    * [.array()](#List+array) ⇒ <code>Array</code>
    * [.first([amount])](#List+first) ⇒ <code>\*</code> \| <code>Array.&lt;\*&gt;</code>
    * [.last([amount])](#List+last) ⇒ <code>\*</code> \| <code>Array.&lt;\*&gt;</code>
    * [.random([amount])](#List+random) ⇒ <code>\*</code> \| <code>Array.&lt;\*&gt;</code>
    * [.find(fn, [thisArg])](#List+find) ⇒ <code>\*</code>
    * [.sweep(fn, [thisArg])](#List+sweep) ⇒ <code>number</code>
    * [.filter(fn, [thisArg])](#List+filter) ⇒ [<code>List</code>](#List)
    * [.partition(fn, [thisArg])](#List+partition) ⇒ [<code>Array.&lt;List&gt;</code>](#List)
    * [.map(fn, [thisArg])](#List+map) ⇒ <code>Array</code>
    * [.mapValues(fn, [thisArg])](#List+mapValues) ⇒ [<code>List</code>](#List)
    * [.some(fn, [thisArg])](#List+some) ⇒ <code>boolean</code>
    * [.every(fn, [thisArg])](#List+every) ⇒ <code>boolean</code>
    * [.reduce(fn, [initialValue])](#List+reduce) ⇒ <code>\*</code>
    * [.each(fn, [thisArg])](#List+each) ⇒ [<code>List</code>](#List)
    * [.tap(fn, [thisArg])](#List+tap) ⇒ [<code>List</code>](#List)
    * [.clone()](#List+clone) ⇒ [<code>List</code>](#List)
    * [.concat(...lists)](#List+concat) ⇒ [<code>List</code>](#List)
    * [.equals(list)](#List+equals) ⇒ <code>boolean</code>
    * [.sort([compareFunction])](#List+sort) ⇒ [<code>List</code>](#List)

<a name="List+array"></a>

### list.array() ⇒ <code>Array</code>
<p>Creates an ordered array of the values of this list, and caches it internally. The array will only be
reconstructed if an item is added to or removed from the list, or if you change the length of the array
itself. If you don't want this caching behavoir, use <code>[...list.values()]</code> or
<code>Array.from(list.values())</code> instead.</p>

**Kind**: instance method of [<code>List</code>](#List)  
<a name="List+first"></a>

### list.first([amount]) ⇒ <code>\*</code> \| <code>Array.&lt;\*&gt;</code>
<p>Obtains the first value(s) in this list.</p>

**Kind**: instance method of [<code>List</code>](#List)  
**Returns**: <code>\*</code> \| <code>Array.&lt;\*&gt;</code> - <p>A single value if no amount is provided or an array of values, starting from the end if
amount is negative</p>  

| Param | Type | Description |
| --- | --- | --- |
| [amount] | <code>number</code> | <p>Amount of values to obtain from the beginning</p> |

<a name="List+last"></a>

### list.last([amount]) ⇒ <code>\*</code> \| <code>Array.&lt;\*&gt;</code>
<p>Obtains the last value(s) in this list. This relies on [array](#List+array), and thus the caching
mechanism applies here as well.</p>

**Kind**: instance method of [<code>List</code>](#List)  
**Returns**: <code>\*</code> \| <code>Array.&lt;\*&gt;</code> - <p>A single value if no amount is provided or an array of values, starting from the start if
amount is negative</p>  

| Param | Type | Description |
| --- | --- | --- |
| [amount] | <code>number</code> | <p>Amount of values to obtain from the end</p> |

<a name="List+random"></a>

### list.random([amount]) ⇒ <code>\*</code> \| <code>Array.&lt;\*&gt;</code>
<p>Obtains unique random value(s) from this list. This relies on [array](#List+array), and thus the caching
mechanism applies here as well.</p>

**Kind**: instance method of [<code>List</code>](#List)  
**Returns**: <code>\*</code> \| <code>Array.&lt;\*&gt;</code> - <p>A single value if no amount is provided or an array of values</p>  

| Param | Type | Description |
| --- | --- | --- |
| [amount] | <code>number</code> | <p>Amount of values to obtain randomly</p> |

<a name="List+find"></a>

### list.find(fn, [thisArg]) ⇒ <code>\*</code>
<p>Searches for a single item where the given function returns a truthy value. This behaves like
<a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/find">Array.find()</a>.</p>

**Kind**: instance method of [<code>List</code>](#List)  

| Param | Type | Description |
| --- | --- | --- |
| fn | <code>function</code> | <p>The function to test with (should return boolean)</p> |
| [thisArg] | <code>\*</code> | <p>Value to use as <code>this</code> when executing function</p> |

**Example**  
```js
list.find(user => user.username === 'Bob');
```
<a name="List+sweep"></a>

### list.sweep(fn, [thisArg]) ⇒ <code>number</code>
<p>Removes entries that satisfy the provided filter function.</p>

**Kind**: instance method of [<code>List</code>](#List)  
**Returns**: <code>number</code> - <p>The number of removed entries</p>  

| Param | Type | Description |
| --- | --- | --- |
| fn | <code>function</code> | <p>Function used to test (should return a boolean)</p> |
| [thisArg] | <code>\*</code> | <p>Value used as <code>this</code> when executing function</p> |

<a name="List+filter"></a>

### list.filter(fn, [thisArg]) ⇒ [<code>List</code>](#List)
<p>Identical to
<a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/filter">Array.filter()</a>,
but returns a [List](#List) instead of an Array.</p>

**Kind**: instance method of [<code>List</code>](#List)  

| Param | Type | Description |
| --- | --- | --- |
| fn | <code>function</code> | <p>The function used to test with (should return boolean)</p> |
| [thisArg] | <code>\*</code> | <p>Value to use as <code>this</code> when executing function</p> |

**Example**  
```js
list.filter(user => user.username === 'Bob');
```
<a name="List+partition"></a>

### list.partition(fn, [thisArg]) ⇒ [<code>Array.&lt;List&gt;</code>](#List)
<p>Partitions the list into two lists where the first list
contains the items that passed and the second contains the items that failed.</p>

**Kind**: instance method of [<code>List</code>](#List)  

| Param | Type | Description |
| --- | --- | --- |
| fn | <code>function</code> | <p>Function used to test (should return a boolean)</p> |
| [thisArg] | <code>\*</code> | <p>Value to use as <code>this</code> when executing function</p> |

**Example**  
```js
const [big, small] = list.partition(guild => guild.memberCount > 250);
```
<a name="List+map"></a>

### list.map(fn, [thisArg]) ⇒ <code>Array</code>
<p>Maps each item to another value into an array. Identical in behavior to
<a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/map">Array.map()</a>.</p>

**Kind**: instance method of [<code>List</code>](#List)  

| Param | Type | Description |
| --- | --- | --- |
| fn | <code>function</code> | <p>Function that produces an element of the new array, taking three arguments</p> |
| [thisArg] | <code>\*</code> | <p>Value to use as <code>this</code> when executing function</p> |

**Example**  
```js
list.map(user => user.tag);
```
<a name="List+mapValues"></a>

### list.mapValues(fn, [thisArg]) ⇒ [<code>List</code>](#List)
<p>Maps each item to another into a list. Identical in behavior to
<a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/map">Array.map()</a>.</p>

**Kind**: instance method of [<code>List</code>](#List)  

| Param | Type | Description |
| --- | --- | --- |
| fn | <code>function</code> | <p>Function that produces an element of the new list, taking three arguments</p> |
| [thisArg] | <code>\*</code> | <p>Value to use as <code>this</code> when executing function</p> |

**Example**  
```js
list.mapValues(user => user.tag);
```
<a name="List+some"></a>

### list.some(fn, [thisArg]) ⇒ <code>boolean</code>
<p>Checks if there exists an item that passes a test. Identical in behavior to
<a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/some">Array.some()</a>.</p>

**Kind**: instance method of [<code>List</code>](#List)  

| Param | Type | Description |
| --- | --- | --- |
| fn | <code>function</code> | <p>Function used to test (should return a boolean)</p> |
| [thisArg] | <code>\*</code> | <p>Value to use as <code>this</code> when executing function</p> |

**Example**  
```js
list.some(user => user.discriminator === '0000');
```
<a name="List+every"></a>

### list.every(fn, [thisArg]) ⇒ <code>boolean</code>
<p>Checks if all items pass a test. Identical in behavior to
<a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/every">Array.every()</a>.</p>

**Kind**: instance method of [<code>List</code>](#List)  

| Param | Type | Description |
| --- | --- | --- |
| fn | <code>function</code> | <p>Function used to test (should return a boolean)</p> |
| [thisArg] | <code>\*</code> | <p>Value to use as <code>this</code> when executing function</p> |

**Example**  
```js
list.every(user => !user.bot);
```
<a name="List+reduce"></a>

### list.reduce(fn, [initialValue]) ⇒ <code>\*</code>
<p>Applies a function to produce a single value. Identical in behavior to
<a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/reduce">Array.reduce()</a>.</p>

**Kind**: instance method of [<code>List</code>](#List)  

| Param | Type | Description |
| --- | --- | --- |
| fn | <code>function</code> | <p>Function used to reduce, taking four arguments; <code>accumulator</code>, <code>currentValue</code>, <code>currentValue</code>, and <code>list</code></p> |
| [initialValue] | <code>\*</code> | <p>Starting value for the accumulator</p> |

**Example**  
```js
list.reduce((acc, guild) => acc + guild.memberCount, 0);
```
<a name="List+each"></a>

### list.each(fn, [thisArg]) ⇒ [<code>List</code>](#List)
<p>Identical to
<a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Set/forEach">Set.forEach()</a>,
but returns the list instead of undefined.</p>

**Kind**: instance method of [<code>List</code>](#List)  

| Param | Type | Description |
| --- | --- | --- |
| fn | <code>function</code> | <p>Function to execute for each element</p> |
| [thisArg] | <code>\*</code> | <p>Value to use as <code>this</code> when executing function</p> |

**Example**  
```js
list .each(user => console.log(user.username)) .filter(user => user.bot) .each(user => console.log(user.username));
```
<a name="List+tap"></a>

### list.tap(fn, [thisArg]) ⇒ [<code>List</code>](#List)
<p>Runs a function on the list and returns the list.</p>

**Kind**: instance method of [<code>List</code>](#List)  

| Param | Type | Description |
| --- | --- | --- |
| fn | <code>function</code> | <p>Function to execute</p> |
| [thisArg] | <code>\*</code> | <p>Value to use as <code>this</code> when executing function</p> |

**Example**  
```js
list .tap(list => console.log(list.size)) .filter(user => user.bot) .tap(list => console.log(list.size));
```
<a name="List+clone"></a>

### list.clone() ⇒ [<code>List</code>](#List)
<p>Creates an identical shallow copy of this list.</p>

**Kind**: instance method of [<code>List</code>](#List)  
**Example**  
```js
const newList = someList.clone();
```
<a name="List+concat"></a>

### list.concat(...lists) ⇒ [<code>List</code>](#List)
<p>Combines this list with others into a new list. None of the source lists are modified.</p>

**Kind**: instance method of [<code>List</code>](#List)  

| Param | Type | Description |
| --- | --- | --- |
| ...lists | [<code>List</code>](#List) | <p>Lists to merge</p> |

**Example**  
```js
const newList = someList.concat(someOtherList, anotherList, ohBoyAList);
```
<a name="List+equals"></a>

### list.equals(list) ⇒ <code>boolean</code>
<p>Checks if this list shares identical value-value parings with another.
This is different to checking for equality using equal-signs, because
the collections may be different objects, but contain the same data.</p>

**Kind**: instance method of [<code>List</code>](#List)  
**Returns**: <code>boolean</code> - <p>Whether the collections have identical contents</p>  

| Param | Type | Description |
| --- | --- | --- |
| list | [<code>List</code>](#List) | <p>List to compare with</p> |

<a name="List+sort"></a>

### list.sort([compareFunction]) ⇒ [<code>List</code>](#List)
<p>The sort() method sorts the elements of a list and returns it.
The sort is not necessarily stable. The default sort order is according to string Unicode points.</p>

**Kind**: instance method of [<code>List</code>](#List)  

| Param | Type | Description |
| --- | --- | --- |
| [compareFunction] | <code>function</code> | <p>Specifies a function that defines the sort order. If omitted, the list is sorted according to each character's Unicode point value, according to the string conversion of each element.</p> |

<a name="Type"></a>

## Type
<p>The class for deep checking types.</p>

**Kind**: global class  

* [Type](#Type)
    * [new Type(value, [parent])](#new_Type_new)
    * _instance_
        * [.value](#Type+value) : <code>\*</code>
        * [.is](#Type+is) : <code>string</code>
        * [.toString()](#Type+toString) ⇒ <code>string</code>
    * _static_
        * [.resolve(value)](#Type.resolve) ⇒ <code>string</code>

<a name="new_Type_new"></a>

### new Type(value, [parent])

| Param | Type | Default | Description |
| --- | --- | --- | --- |
| value | <code>\*</code> |  | <p>The value to generate a deep Type for</p> |
| [parent] | [<code>Type</code>](#Type) | <code></code> | <p>The parent value used in recursion</p> |

<a name="Type+value"></a>

### type.value : <code>\*</code>
<p>The value to generate a deep Type of</p>

**Kind**: instance property of [<code>Type</code>](#Type)  
<a name="Type+is"></a>

### type.is : <code>string</code>
<p>The shallow type of this</p>

**Kind**: instance property of [<code>Type</code>](#Type)  
<a name="Type+toString"></a>

### type.toString() ⇒ <code>string</code>
<p>The full string type generated.</p>

**Kind**: instance method of [<code>Type</code>](#Type)  
<a name="Type.resolve"></a>

### Type.resolve(value) ⇒ <code>string</code>
<p>Resolves the type name that defines the input.</p>

**Kind**: static method of [<code>Type</code>](#Type)  

| Param | Type | Description |
| --- | --- | --- |
| value | <code>\*</code> | <p>The value to get the type name from</p> |

<a name="Util"></a>

## Util
<p>Internal utility class.</p>

**Kind**: global class  

* [Util](#Util)
    * [new Util()](#new_Util_new)
    * [.isObject(inp)](#Util.isObject) ⇒ <code>boolean</code>
    * [.isPrimitive(inp)](#Util.isPrimitive) ⇒ <code>boolean</code>
    * [.toTitleCase(str)](#Util.toTitleCase) ⇒ <code>string</code>
    * [.mergeObjects(objTarget, objSource)](#Util.mergeObjects) ⇒ <code>\*</code>
    * [.makeObject(path, value, [obj])](#Util.makeObject) ⇒ <code>\*</code>
    * [.deepClone(source)](#Util.deepClone) ⇒ <code>\*</code>
    * [.mergeDefault(def, given)](#Util.mergeDefault) ⇒ <code>Object</code>
    * [.isClass(inp)](#Util.isClass) ⇒ <code>boolean</code>
    * [.isThenable(input)](#Util.isThenable) ⇒ <code>boolean</code>
    * [.isFunction(input)](#Util.isFunction) ⇒ <code>boolean</code>
    * [.objectToTuples(obj, [prefix])](#Util.objectToTuples) ⇒ <code>Array.&lt;Array.&lt;\*&gt;&gt;</code>
    * [.arrayStrictEquals(arr1, arr2)](#Util.arrayStrictEquals) ⇒ <code>boolean</code>

<a name="new_Util_new"></a>

### new Util()
<p>This class may not be initialized with new</p>

**Throws**:

- <code>Error</code> 

<a name="Util.isObject"></a>

### Util.isObject(inp) ⇒ <code>boolean</code>
<p>Checks if a value is an <a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object">Object</a>.</p>

**Kind**: static method of [<code>Util</code>](#Util)  

| Param | Type | Description |
| --- | --- | --- |
| inp | <code>\*</code> | <p>Input to check</p> |

<a name="Util.isPrimitive"></a>

### Util.isPrimitive(inp) ⇒ <code>boolean</code>
<p>Checks if a value is a <a href="https://developer.mozilla.org/en-US/docs/Glossary/Primitive">primitive</a> type.</p>

**Kind**: static method of [<code>Util</code>](#Util)  

| Param | Type | Description |
| --- | --- | --- |
| inp | <code>\*</code> | <p>Input to check</p> |

<a name="Util.toTitleCase"></a>

### Util.toTitleCase(str) ⇒ <code>string</code>
<p>Converts a string to Title Case.</p>

**Kind**: static method of [<code>Util</code>](#Util)  

| Param | Type | Description |
| --- | --- | --- |
| str | <code>string</code> | <p>The string to convert to title case</p> |

<a name="Util.mergeObjects"></a>

### Util.mergeObjects(objTarget, objSource) ⇒ <code>\*</code>
<p>Merges two objects.</p>

**Kind**: static method of [<code>Util</code>](#Util)  

| Param | Type | Description |
| --- | --- | --- |
| objTarget | <code>\*</code> | <p>The object to be merged</p> |
| objSource | <code>\*</code> | <p>The object to merge</p> |

<a name="Util.makeObject"></a>

### Util.makeObject(path, value, [obj]) ⇒ <code>\*</code>
<p>Turns a dotted path into a json object.</p>

**Kind**: static method of [<code>Util</code>](#Util)  

| Param | Type | Default | Description |
| --- | --- | --- | --- |
| path | <code>string</code> |  | <p>The dotted path</p> |
| value | <code>\*</code> |  | <p>The value</p> |
| [obj] | <code>Object.&lt;string, \*&gt;</code> | <code>{}</code> | <p>The object to edit</p> |

<a name="Util.deepClone"></a>

### Util.deepClone(source) ⇒ <code>\*</code>
<p>Deeply clones a value.</p>

**Kind**: static method of [<code>Util</code>](#Util)  

| Param | Type | Description |
| --- | --- | --- |
| source | <code>\*</code> | <p>Value to clone</p> |

<a name="Util.mergeDefault"></a>

### Util.mergeDefault(def, given) ⇒ <code>Object</code>
<p>Merges a given object with a set of defaults.</p>

**Kind**: static method of [<code>Util</code>](#Util)  

| Param | Type | Description |
| --- | --- | --- |
| def | <code>Object</code> | <p>Defaults to add</p> |
| given | <code>Object</code> | <p>Given object to add to</p> |

<a name="Util.isClass"></a>

### Util.isClass(inp) ⇒ <code>boolean</code>
<p>Checks if a given input is a class.</p>

**Kind**: static method of [<code>Util</code>](#Util)  

| Param | Type | Description |
| --- | --- | --- |
| inp | <code>function</code> | <p>The input to check</p> |

<a name="Util.isThenable"></a>

### Util.isThenable(input) ⇒ <code>boolean</code>
<p>Checks if a given input is a Promise.</p>

**Kind**: static method of [<code>Util</code>](#Util)  

| Param | Type | Description |
| --- | --- | --- |
| input | <code>Promise</code> | <p>The input to check</p> |

<a name="Util.isFunction"></a>

### Util.isFunction(input) ⇒ <code>boolean</code>
<p>Checks if the given input is a Function.</p>

**Kind**: static method of [<code>Util</code>](#Util)  

| Param | Type | Description |
| --- | --- | --- |
| input | <code>function</code> | <p>The input to check</p> |

<a name="Util.objectToTuples"></a>

### Util.objectToTuples(obj, [prefix]) ⇒ <code>Array.&lt;Array.&lt;\*&gt;&gt;</code>
<p>Convert an object to a tuple.</p>

**Kind**: static method of [<code>Util</code>](#Util)  

| Param | Type | Default | Description |
| --- | --- | --- | --- |
| obj | <code>Object.&lt;string, \*&gt;</code> |  | <p>The object to convert</p> |
| [prefix] | <code>string</code> | <code>&quot;&#x27;&#x27;&quot;</code> | <p>The prefix for the key</p> |

<a name="Util.arrayStrictEquals"></a>

### Util.arrayStrictEquals(arr1, arr2) ⇒ <code>boolean</code>
<p>Compares if both arrays are strictly equal.</p>

**Kind**: static method of [<code>Util</code>](#Util)  

| Param | Type | Description |
| --- | --- | --- |
| arr1 | <code>Array.&lt;any&gt;</code> | <p>The first array to compare</p> |
| arr2 | <code>Array.&lt;any&gt;</code> | <p>The second array to compare</p> |

<a name="_Symbol$species"></a>

## *\_Symbol$species ⇐ <code>Collection</code>*
<p>The base registry for all stores to extend.</p>

**Kind**: global abstract variable  
**Extends**: <code>Collection</code>  
<a name="InlustrisPlugin"></a>

## InlustrisPlugin : <code>Object</code>
<p>The required export to load an external plugin</p>

**Kind**: global typedef  
**Properties**

| Name | Type | Description |
| --- | --- | --- |
| name | <code>string</code> | <p>The name of the plugin, this will be what's attached to the client</p> |
| loader | <code>function</code> | <p>The loader function, will be called with the [client](#InlustrisClient) as <code>this</code></p> |

<a name="InlustrisOptions"></a>

## InlustrisOptions : [<code>ClientOptions</code>](https://discord.js.org/#/docs/main/master/typedef/ClientOptions)
<p>Options for a new [InlustrisClient](#InlustrisClient)</p>

**Kind**: global typedef  
**Properties**

| Name | Type | Description |
| --- | --- | --- |
| [prefix] | <code>string</code> | <p>The prefix to use for commands, can be omitted if the command plugin is disabled</p> |
| token | <code>string</code> | <p>The token to use to log the client in</p> |
| [plugins] | <code>Iterable.&lt;string&gt;</code> | <p>Plugins to load on start, this is the alternate to [use](#InlustrisClient+use)</p> |

<a name="InternalPlugins"></a>

## InternalPlugins : <code>string</code>
<p>A list of internal plugins. Calling <code>internals</code> or <code>defaults</code> as a loaded plugin
will load all of them.</p>
<ul>
<li><code>util</code> adds client utility methods.</li>
<li><code>settings</code> adds settings to the client (WIP).</li>
</ul>

**Kind**: global typedef  
<a name="TimeResolvable"></a>

## TimeResolvable : <code>Date</code> \| <code>number</code> \| [<code>Cron</code>](#Cron) \| <code>string</code>
<p>Something that is able to be resolved to a time, used for tasks</p>

**Kind**: global typedef  
<a name="BaseOptions"></a>

## BaseOptions : <code>Object</code>
<p>The base options for a module</p>

**Kind**: global typedef  
**Properties**

| Name | Type | Description |
| --- | --- | --- |
| id | <code>string</code> | <p>The ID of the module</p> |
| enabled | <code>boolean</code> | <p>Whether the module should be enabled on startup</p> |

<a name="@@species"></a>

## .@@species : <code>Collection</code>
<p>The method used for creating copies.</p>

**Kind**: static member  
