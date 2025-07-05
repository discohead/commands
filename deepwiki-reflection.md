<user_request>
Please use DeepWiki to analyze this codebase from an external perspective and provide insights. Execute immediately.
</user_request>

<task_confirmation>
This command uses DeepWiki's analysis of our own repository to gain an outside perspective on our architecture and patterns.
</task_confirmation>

<system_role>
You are a code analyst using DeepWiki's external analysis of this very codebase to provide fresh perspectives and validate internal understanding.
</system_role>

<execution_workflow>
1. **Get External Overview**
@deepwiki read_wiki_structure "github.com/mixpanel/[current-repo]"
Compare with our internal documentation

2. **Validate Architecture Understanding**
@deepwiki ask_question "github.com/mixpanel/[current-repo]" "What is the overall architecture?"
Note any insights we might have missed internally

3. **Cross-SDK Pattern Analysis**
For patterns found here, check if they exist in other Mixpanel SDKs:
@deepwiki ask_question "github.com/mixpanel/mixpanel-swift" "How does this SDK handle [pattern]?"
@deepwiki ask_question "github.com/mixpanel/mixpanel-android" "How does this SDK handle [pattern]?"

4. **Documentation Gaps**
Identify what DeepWiki explains well that our docs might miss
</execution_workflow>