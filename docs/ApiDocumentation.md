# API Documentation
> Note: This documentation was auto-generated using this parser to help dogfood the API. It may be incomplete. Please contribute fixes to
`tools/PrintApiDocumentation.php` and suggest API improvements.
<hr>

## Node
### Node::getNodeKindName
> TODO: add doc comment

```php
public function getNodeKindName ( ) : string
```
### Node::getStart
Gets start position of Node, not including leading comments and whitespace.
```php
public function getStart ( ) : int
```
### Node::getFullStart
Gets start position of Node, including leading comments and whitespace
```php
public function getFullStart ( ) : int
```
### Node::getParent
Gets parent of current node (returns null if has no parent)
```php
public function getParent ( )
```
### Node::getAncestor
> TODO: add doc comment

```php
public function getAncestor ( $className )
```
### Node::getRoot
Gets root of the syntax tree (returns self if has no parents)
```php
public function & getRoot ( ) : Node
```
### Node::getDescendantNodesAndTokens
Gets generator containing all descendant Nodes and Tokens.
```php
public function getDescendantNodesAndTokens ( callable $shouldDescendIntoChildrenFn = null )
```
### Node::getDescendantNodes
Gets a generator containing all descendant Nodes.
```php
public function getDescendantNodes ( callable $shouldDescendIntoChildrenFn = null )
```
### Node::getDescendantTokens
Gets generator containing all descendant Tokens.
```php
public function getDescendantTokens ( callable $shouldDescendIntoChildrenFn = null )
```
### Node::getChildNodesAndTokens
Gets generator containing all child Nodes and Tokens (direct descendants)
```php
public function getChildNodesAndTokens ( ) : \Generator
```
### Node::getChildNodes
Gets generator containing all child Nodes (direct descendants)
```php
public function getChildNodes ( ) : \Generator
```
### Node::getChildTokens
Gets generator containing all child Tokens (direct descendants)
```php
public function getChildTokens ( )
```
### Node::getChildNames
Gets array of declared child names (cached). This is used as an optimization when iterating over nodes: For direct iteration PHP will create a properties hashtable on the object, thus doubling memory usage. We avoid this by iterating over just the names instead.
```php
public function getChildNames ( )
```
### Node::getWidth
Gets width of a Node (not including comment / whitespace trivia)
```php
public function getWidth ( ) : int
```
### Node::getFullWidth
Gets width of a Node (including comment / whitespace trivia)
```php
public function getFullWidth ( ) : int
```
### Node::getText
Gets string representing Node text (not including leading comment + whitespace trivia)
```php
public function getText ( ) : string
```
### Node::getFullText
Gets full text of Node (including leading comment + whitespace trivia)
```php
public function getFullText ( ) : string
```
### Node::getLeadingCommentAndWhitespaceText
Gets string representing Node's leading comment and whitespace text.
```php
public function getLeadingCommentAndWhitespaceText ( ) : string
```
### Node::jsonSerialize
> TODO: add doc comment

```php
public function jsonSerialize ( )
```
### Node::getEndPosition
Get the end index of a Node.
```php
public function getEndPosition ( )
```
### Node::getFileContents
> TODO: add doc comment

```php
public function & getFileContents ( ) : string
```
### Node::getDescendantNodeAtPosition
Searches descendants to find a Node at the given position.
```php
public function getDescendantNodeAtPosition ( int $pos )
```
### Node::__toString
> TODO: add doc comment

```php
public function __toString ( )
```
## Token
### Token::__construct
> TODO: add doc comment

```php
public function __construct ( $kind, $fullStart, $start, $length )
```
### Token::getLeadingCommentsAndWhitespaceText
> TODO: add doc comment

```php
public function getLeadingCommentsAndWhitespaceText ( string $document ) : string
```
### Token::getText
> TODO: add doc comment

```php
public function getText ( string $document ) : string
```
### Token::getFullText
> TODO: add doc comment

```php
public function getFullText ( string & $document ) : string
```
### Token::getStartPosition
> TODO: add doc comment

```php
public function getStartPosition ( )
```
### Token::getFullStartPosition
> TODO: add doc comment

```php
public function getFullStartPosition ( )
```
### Token::getWidth
> TODO: add doc comment

```php
public function getWidth ( )
```
### Token::getFullWidth
> TODO: add doc comment

```php
public function getFullWidth ( )
```
### Token::getEndPosition
> TODO: add doc comment

```php
public function getEndPosition ( )
```
### Token::getTokenKindNameFromValue
> TODO: add doc comment

```php
public static function getTokenKindNameFromValue ( $kindName )
```
### Token::jsonSerialize
> TODO: add doc comment

```php
public function jsonSerialize ( )
```
## Parser
### Parser::__construct
> TODO: add doc comment

```php
public function __construct ( )
```
### Parser::parseSourceFile
> TODO: add doc comment

```php
public function parseSourceFile ( $fileContents ) : SourceFileNode
```
## Associativity
## ParseContext
## DiagnosticsProvider
### DiagnosticsProvider::getDiagnostics
> TODO: add doc comment

```php
public static function getDiagnostics ( $node )
```
## PositionUtilities
### PositionUtilities::getRangeFromPosition
> TODO: add doc comment

```php
public static function getRangeFromPosition ( $pos, $length, $text )
```
### PositionUtilities::getLineCharacterPositionFromPosition
Get's 0-indexed LineCharacterPosition from 0-indexed position into $text. Out of bounds positions are handled gracefully. Positions greater than the length of text length are resolved to text length, and negative positions are resolved to 0. TODO consider throwing exception instead.
```php
public static function getLineCharacterPositionFromPosition ( $pos, $text ) : LineCharacterPosition
```
## LineCharacterPosition
### LineCharacterPosition::__construct
> TODO: add doc comment

```php
public function __construct ( int $line, int $character )
```
## MissingToken
### MissingToken::__construct
> TODO: add doc comment

```php
public function __construct ( int $kind, int $fullStart )
```
### MissingToken::jsonSerialize
> TODO: add doc comment

```php
public function jsonSerialize ( )
```
## SkippedToken
### SkippedToken::__construct
> TODO: add doc comment

```php
public function __construct ( Token $token )
```
### SkippedToken::jsonSerialize
> TODO: add doc comment

```php
public function jsonSerialize ( )
```
## Node types
> TODO: complete documentation - in addition to the helper methods on the Node base class,
every Node object has properties specific to the Node type. Browse `src/Node/` to explore these properties.