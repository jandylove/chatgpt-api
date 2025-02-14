[chatgpt](readme.md) / Exports

# chatgpt

## Table of contents

### Classes

- [ChatGPTAPI](classes/ChatGPTAPI.md)
- [ChatGPTConversation](classes/ChatGPTConversation.md)
- [ChatGPTError](classes/ChatGPTError.md)

### Type Aliases

- [AvailableModerationModels](modules.md#availablemoderationmodels)
- [ContentType](modules.md#contenttype)
- [ConversationJSONBody](modules.md#conversationjsonbody)
- [ConversationResponseEvent](modules.md#conversationresponseevent)
- [Message](modules.md#message)
- [MessageActionType](modules.md#messageactiontype)
- [MessageContent](modules.md#messagecontent)
- [MessageFeedbackJSONBody](modules.md#messagefeedbackjsonbody)
- [MessageFeedbackRating](modules.md#messagefeedbackrating)
- [MessageFeedbackResult](modules.md#messagefeedbackresult)
- [MessageFeedbackTags](modules.md#messagefeedbacktags)
- [MessageMetadata](modules.md#messagemetadata)
- [Model](modules.md#model)
- [ModelsResult](modules.md#modelsresult)
- [ModerationsJSONBody](modules.md#moderationsjsonbody)
- [ModerationsJSONResult](modules.md#moderationsjsonresult)
- [OpenAIAuth](modules.md#openaiauth)
- [Prompt](modules.md#prompt)
- [PromptContent](modules.md#promptcontent)
- [Role](modules.md#role)
- [SendConversationMessageOptions](modules.md#sendconversationmessageoptions)
- [SendMessageOptions](modules.md#sendmessageoptions)
- [SessionResult](modules.md#sessionresult)
- [User](modules.md#user)

### Functions

- [getBrowser](modules.md#getbrowser)
- [getOpenAIAuth](modules.md#getopenaiauth)
- [markdownToText](modules.md#markdowntotext)

## Type Aliases

### AvailableModerationModels

Ƭ **AvailableModerationModels**: ``"text-moderation-playground"``

#### Defined in

[src/types.ts:109](https://github.com/transitive-bullshit/chatgpt-api/blob/c257286/src/types.ts#L109)

___

### ContentType

Ƭ **ContentType**: ``"text"``

#### Defined in

[src/types.ts:1](https://github.com/transitive-bullshit/chatgpt-api/blob/c257286/src/types.ts#L1)

___

### ConversationJSONBody

Ƭ **ConversationJSONBody**: `Object`

https://chat.openapi.com/backend-api/conversation

#### Type declaration

| Name | Type | Description |
| :------ | :------ | :------ |
| `action` | `string` | The action to take |
| `conversation_id?` | `string` | The ID of the conversation |
| `messages` | [`Prompt`](modules.md#prompt)[] | Prompts to provide |
| `model` | `string` | The model to use |
| `parent_message_id` | `string` | The parent message ID |

#### Defined in

[src/types.ts:134](https://github.com/transitive-bullshit/chatgpt-api/blob/c257286/src/types.ts#L134)

___

### ConversationResponseEvent

Ƭ **ConversationResponseEvent**: `Object`

#### Type declaration

| Name | Type |
| :------ | :------ |
| `conversation_id?` | `string` |
| `error?` | `string` \| ``null`` |
| `message?` | [`Message`](modules.md#message) |

#### Defined in

[src/types.ts:251](https://github.com/transitive-bullshit/chatgpt-api/blob/c257286/src/types.ts#L251)

___

### Message

Ƭ **Message**: `Object`

#### Type declaration

| Name | Type |
| :------ | :------ |
| `content` | [`MessageContent`](modules.md#messagecontent) |
| `create_time` | `string` \| ``null`` |
| `end_turn` | ``null`` |
| `id` | `string` |
| `metadata` | [`MessageMetadata`](modules.md#messagemetadata) |
| `recipient` | `string` |
| `role` | `string` |
| `update_time` | `string` \| ``null`` |
| `user` | `string` \| ``null`` |
| `weight` | `number` |

#### Defined in

[src/types.ts:257](https://github.com/transitive-bullshit/chatgpt-api/blob/c257286/src/types.ts#L257)

___

### MessageActionType

Ƭ **MessageActionType**: ``"next"`` \| ``"variant"``

#### Defined in

[src/types.ts:276](https://github.com/transitive-bullshit/chatgpt-api/blob/c257286/src/types.ts#L276)

___

### MessageContent

Ƭ **MessageContent**: `Object`

#### Type declaration

| Name | Type |
| :------ | :------ |
| `content_type` | `string` |
| `parts` | `string`[] |

#### Defined in

[src/types.ts:270](https://github.com/transitive-bullshit/chatgpt-api/blob/c257286/src/types.ts#L270)

___

### MessageFeedbackJSONBody

Ƭ **MessageFeedbackJSONBody**: `Object`

https://chat.openapi.com/backend-api/conversation/message_feedback

#### Type declaration

| Name | Type | Description |
| :------ | :------ | :------ |
| `conversation_id` | `string` | The ID of the conversation |
| `message_id` | `string` | The message ID |
| `rating` | [`MessageFeedbackRating`](modules.md#messagefeedbackrating) | The rating |
| `tags?` | [`MessageFeedbackTags`](modules.md#messagefeedbacktags)[] | Tags to give the rating |
| `text?` | `string` | The text to include |

#### Defined in

[src/types.ts:193](https://github.com/transitive-bullshit/chatgpt-api/blob/c257286/src/types.ts#L193)

___

### MessageFeedbackRating

Ƭ **MessageFeedbackRating**: ``"thumbsUp"`` \| ``"thumbsDown"``

#### Defined in

[src/types.ts:249](https://github.com/transitive-bullshit/chatgpt-api/blob/c257286/src/types.ts#L249)

___

### MessageFeedbackResult

Ƭ **MessageFeedbackResult**: `Object`

#### Type declaration

| Name | Type | Description |
| :------ | :------ | :------ |
| `conversation_id` | `string` | The ID of the conversation |
| `message_id` | `string` | The message ID |
| `rating` | [`MessageFeedbackRating`](modules.md#messagefeedbackrating) | The rating |
| `text?` | `string` | The text the server received, including tags |
| `user_id` | `string` | The ID of the user |

#### Defined in

[src/types.ts:222](https://github.com/transitive-bullshit/chatgpt-api/blob/c257286/src/types.ts#L222)

___

### MessageFeedbackTags

Ƭ **MessageFeedbackTags**: ``"harmful"`` \| ``"false"`` \| ``"not-helpful"``

#### Defined in

[src/types.ts:220](https://github.com/transitive-bullshit/chatgpt-api/blob/c257286/src/types.ts#L220)

___

### MessageMetadata

Ƭ **MessageMetadata**: `any`

#### Defined in

[src/types.ts:275](https://github.com/transitive-bullshit/chatgpt-api/blob/c257286/src/types.ts#L275)

___

### Model

Ƭ **Model**: `Object`

#### Type declaration

| Name | Type | Description |
| :------ | :------ | :------ |
| `is_special` | `boolean` | Whether or not the model is special |
| `max_tokens` | `number` | Max tokens of the model |
| `slug` | `string` | Name of the model |

#### Defined in

[src/types.ts:77](https://github.com/transitive-bullshit/chatgpt-api/blob/c257286/src/types.ts#L77)

___

### ModelsResult

Ƭ **ModelsResult**: `Object`

https://chat.openapi.com/backend-api/models

#### Type declaration

| Name | Type | Description |
| :------ | :------ | :------ |
| `models` | [`Model`](modules.md#model)[] | Array of models |

#### Defined in

[src/types.ts:70](https://github.com/transitive-bullshit/chatgpt-api/blob/c257286/src/types.ts#L70)

___

### ModerationsJSONBody

Ƭ **ModerationsJSONBody**: `Object`

https://chat.openapi.com/backend-api/moderations

#### Type declaration

| Name | Type | Description |
| :------ | :------ | :------ |
| `input` | `string` | Input for the moderation decision |
| `model` | [`AvailableModerationModels`](modules.md#availablemoderationmodels) | The model to use in the decision |

#### Defined in

[src/types.ts:97](https://github.com/transitive-bullshit/chatgpt-api/blob/c257286/src/types.ts#L97)

___

### ModerationsJSONResult

Ƭ **ModerationsJSONResult**: `Object`

https://chat.openapi.com/backend-api/moderations

#### Type declaration

| Name | Type | Description |
| :------ | :------ | :------ |
| `blocked` | `boolean` | Whether or not the input is blocked |
| `flagged` | `boolean` | Whether or not the input is flagged |
| `moderation_id` | `string` | The ID of the decision |

#### Defined in

[src/types.ts:114](https://github.com/transitive-bullshit/chatgpt-api/blob/c257286/src/types.ts#L114)

___

### OpenAIAuth

Ƭ **OpenAIAuth**: `Object`

Represents everything that's required to pass into `ChatGPTAPI` in order
to authenticate with the unofficial ChatGPT API.

#### Type declaration

| Name | Type |
| :------ | :------ |
| `clearanceToken` | `string` |
| `cookies?` | `Record`<`string`, `Protocol.Network.Cookie`\> |
| `sessionToken` | `string` |
| `userAgent` | `string` |

#### Defined in

[src/openai-auth.ts:17](https://github.com/transitive-bullshit/chatgpt-api/blob/c257286/src/openai-auth.ts#L17)

___

### Prompt

Ƭ **Prompt**: `Object`

#### Type declaration

| Name | Type | Description |
| :------ | :------ | :------ |
| `content` | [`PromptContent`](modules.md#promptcontent) | The content of the prompt |
| `id` | `string` | The ID of the prompt |
| `role` | [`Role`](modules.md#role) | The role played in the prompt |

#### Defined in

[src/types.ts:161](https://github.com/transitive-bullshit/chatgpt-api/blob/c257286/src/types.ts#L161)

___

### PromptContent

Ƭ **PromptContent**: `Object`

#### Type declaration

| Name | Type | Description |
| :------ | :------ | :------ |
| `content_type` | [`ContentType`](modules.md#contenttype) | The content type of the prompt |
| `parts` | `string`[] | The parts to the prompt |

#### Defined in

[src/types.ts:178](https://github.com/transitive-bullshit/chatgpt-api/blob/c257286/src/types.ts#L178)

___

### Role

Ƭ **Role**: ``"user"`` \| ``"assistant"``

#### Defined in

[src/types.ts:3](https://github.com/transitive-bullshit/chatgpt-api/blob/c257286/src/types.ts#L3)

___

### SendConversationMessageOptions

Ƭ **SendConversationMessageOptions**: `Omit`<[`SendMessageOptions`](modules.md#sendmessageoptions), ``"conversationId"`` \| ``"parentMessageId"``\>

#### Defined in

[src/types.ts:289](https://github.com/transitive-bullshit/chatgpt-api/blob/c257286/src/types.ts#L289)

___

### SendMessageOptions

Ƭ **SendMessageOptions**: `Object`

#### Type declaration

| Name | Type |
| :------ | :------ |
| `abortSignal?` | `AbortSignal` |
| `action?` | [`MessageActionType`](modules.md#messageactiontype) |
| `conversationId?` | `string` |
| `messageId?` | `string` |
| `onConversationResponse?` | (`response`: [`ConversationResponseEvent`](modules.md#conversationresponseevent)) => `void` |
| `onProgress?` | (`partialResponse`: `string`) => `void` |
| `parentMessageId?` | `string` |
| `timeoutMs?` | `number` |

#### Defined in

[src/types.ts:278](https://github.com/transitive-bullshit/chatgpt-api/blob/c257286/src/types.ts#L278)

___

### SessionResult

Ƭ **SessionResult**: `Object`

https://chat.openapi.com/api/auth/session

#### Type declaration

| Name | Type | Description |
| :------ | :------ | :------ |
| `accessToken` | `string` | The access token |
| `error?` | `string` \| ``null`` | If there was an error associated with this request |
| `expires` | `string` | ISO date of the expiration date of the access token |
| `user` | [`User`](modules.md#user) | Authenticated user |

#### Defined in

[src/types.ts:8](https://github.com/transitive-bullshit/chatgpt-api/blob/c257286/src/types.ts#L8)

___

### User

Ƭ **User**: `Object`

#### Type declaration

| Name | Type | Description |
| :------ | :------ | :------ |
| `email?` | `string` | Email of the user |
| `features` | `string`[] | Features the user is in |
| `groups` | `string`[] | Groups the user is in |
| `id` | `string` | ID of the user |
| `image` | `string` | Image of the user |
| `name` | `string` | Name of the user |
| `picture` | `string` | Picture of the user |

#### Defined in

[src/types.ts:30](https://github.com/transitive-bullshit/chatgpt-api/blob/c257286/src/types.ts#L30)

## Functions

### getBrowser

▸ **getBrowser**(`launchOptions?`): `Promise`<`Browser`\>

Launches a non-puppeteer instance of Chrome. Note that in my testing, I wasn't
able to use the built-in `puppeteer` version of Chromium because Cloudflare
recognizes it and blocks access.

#### Parameters

| Name | Type |
| :------ | :------ |
| `launchOptions?` | `PuppeteerLaunchOptions` |

#### Returns

`Promise`<`Browser`\>

#### Defined in

[src/openai-auth.ts:127](https://github.com/transitive-bullshit/chatgpt-api/blob/c257286/src/openai-auth.ts#L127)

___

### getOpenAIAuth

▸ **getOpenAIAuth**(`__namedParameters`): `Promise`<[`OpenAIAuth`](modules.md#openaiauth)\>

Bypasses OpenAI's use of Cloudflare to get the cookies required to use
ChatGPT. Uses Puppeteer with a stealth plugin under the hood.

If you pass `email` and `password`, then it will log into the account and
include a `sessionToken` in the response.

If you don't pass `email` and `password`, then it will just return a valid
`clearanceToken`.

This can be useful because `clearanceToken` expires after ~2 hours, whereas
`sessionToken` generally lasts much longer. We recommend renewing your
`clearanceToken` every hour or so and creating a new instance of `ChatGPTAPI`
with your updated credentials.

#### Parameters

| Name | Type |
| :------ | :------ |
| `__namedParameters` | `Object` |
| `__namedParameters.browser?` | `Browser` |
| `__namedParameters.email?` | `string` |
| `__namedParameters.password?` | `string` |
| `__namedParameters.timeoutMs?` | `number` |

#### Returns

`Promise`<[`OpenAIAuth`](modules.md#openaiauth)\>

#### Defined in

[src/openai-auth.ts:39](https://github.com/transitive-bullshit/chatgpt-api/blob/c257286/src/openai-auth.ts#L39)

___

### markdownToText

▸ **markdownToText**(`markdown?`): `string`

#### Parameters

| Name | Type |
| :------ | :------ |
| `markdown?` | `string` |

#### Returns

`string`

#### Defined in

[src/utils.ts:4](https://github.com/transitive-bullshit/chatgpt-api/blob/c257286/src/utils.ts#L4)
