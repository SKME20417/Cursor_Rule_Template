# Database Schema

## Core Tables
- users
- organizations
- memberships
- sessions
- documents
- document_chunks
- embeddings_metadata
- chat_sessions
- chat_messages
- agent_runs
- billing_customers
- usage_events

## Core Rules
- Most business data must be tenant scoped.
- All major tables should include created_at and updated_at.
- Permission-sensitive tables should support auditable ownership.