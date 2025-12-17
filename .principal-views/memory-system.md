# Letta Memory System Architecture

This canvas illustrates the comprehensive memory system architecture in Letta Code, showing how data flows through different memory types and management components.

## Core Components

### Agent (Central)
- **Purpose**: Main orchestrator that initiates all memory operations
- **Location**: `src/agent/memory.ts`
- **Functions**: Coordinates memory access, context building, and storage operations

### Memory Core (Hub)
- **Purpose**: Central memory management component
- **Functions**: Routes requests to appropriate memory types, manages memory hierarchy
- **Location**: Core memory abstraction layer

### Memory Types (Top Layer)

#### Context Memory
- **Color**: Pink (#E91E63)
- **Purpose**: Active conversation context and recent interactions
- **Usage**: Maintains current session state, recent messages, and immediate context
- **Size**: Limited to recent interactions for performance

#### Block Memory  
- **Color**: Deep Orange (#FF5722)
- **Purpose**: Structured data storage with semantic blocks
- **Usage**: Stores organized information, code snippets, and structured knowledge
- **Features**: Searchable, categorized, and retrievable blocks

#### Archival Memory
- **Color**: Brown (#795548)
- **Purpose**: Long-term historical storage
- **Usage**: Permanent storage of important conversations, learned patterns, and historical data
- **Characteristics**: Large capacity, less frequent access

### Message History (Right)
- **Purpose**: Complete chronological log of all messages
- **Location**: `src/agent/message.ts`
- **Functions**: Maintains conversation history, provides context reconstruction
- **Features**: Indexed, searchable, temporal ordering

### Supporting Components

#### Conversation Input (Left)
- **Purpose**: User input and conversation initiation
- **Functions**: Receives user messages, triggers memory operations
- **Connection**: Primary input to the agent system

#### Tools (Bottom Left)
- **Purpose**: Memory-related tool operations
- **Location**: `src/tools/` (memory-related tools)
- **Functions**: Search, retrieve, store, and organize memory operations
- **Examples**: `Read`, `Grep`, `Search` tools

#### Memory Manager (Bottom Center)
- **Purpose**: Advanced memory management and operations
- **Functions**: Memory optimization, cleanup, and organization
- **Features**: Automatic memory management, storage optimization

#### Search Index (Bottom Right)
- **Purpose**: Fast search and retrieval capabilities
- **Functions**: Indexing memory content for quick searches
- **Performance**: Enables rapid memory retrieval and pattern matching

## Data Flow Patterns

### Storage Flow
1. **Conversation** → **Agent** → **Memory Core** → **Specific Memory Type**
2. User input is processed by agent and stored in appropriate memory

### Retrieval Flow
1. **Agent** → **Memory Core** → **Search Index** → **Memory Type** → **Agent**
2. Agent requests context, search index helps locate relevant memory

### Tool Operations
1. **Tools** → **Memory Manager** → **Memory Core** → **Memory Types**
2. Tools perform specialized memory operations through the manager

## Memory Operations

### Context Building
- Combines recent messages from Message History
- Retrieves relevant blocks from Block Memory
- Accesses archival data when needed
- Constructs comprehensive context for agent decision-making

### Memory Persistence
- Automatic storage of conversations and interactions
- Intelligent categorization and tagging
- Cross-reference linking between memory types

### Search and Retrieval
- Indexed search through Search Index
- Semantic matching across memory types
- Context-aware result ranking

## Integration Points

### with Tools System
- Memory tools directly interact with memory components
- File operations integrate with memory storage
- Search capabilities enhance tool effectiveness

### with Agent System
- Continuous context building and maintenance
- Memory-based decision making
- Learning and pattern recognition

### with Permission System
- Memory access validation
- Secure storage operations
- Privacy protection for sensitive data

This architecture provides a robust, scalable, and efficient memory system that supports the agent's ability to maintain context, learn from interactions, and provide intelligent responses based on accumulated knowledge.