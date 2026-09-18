# Temporal UI (temporalio/ui)

## 프로젝트 개요
수백만 건의 복잡한 비즈니스 거래와 결제 워크플로우가 어느 단계까지 진행되었는지 실시간으로 모니터링하는 "엔터프라이즈 워크플로우 종합 관제탑"
시스템 장애가 발생해도 어디서 멈췄는지 즉시 파악하고, 버튼 하나로 실패한 작업을 이전 상태부터 안전하게 복구
대규모 금융 및 이커머스 기업의 무중단 핵심 비즈니스 로직을 지켜주는 든든한 시각화 대시보드

## 핵심 특징 & 추천 분야
- 비즈니스관제탑
- 워크플로우모니터링
- 장애즉각복구
- 대규모거래추적
- 엔터프라이즈대시보드

---
*이 문서는 오픈소스 큐레이터(Curator-Agent)에 의해 자동 생성된 가이드 문서입니다.*


---
## 기존 CLAUDE.md 내용

# Claude AI Assistant Rules for Temporal UI

SvelteKit + Svelte 5 + TypeScript + TailwindCSS + Holocene design system

## Commands

```bash
pnpm lint              # Run all linters
pnpm check             # TypeScript type checking
pnpm test -- --run              # Run unit tests
```

## Svelte 5 Patterns

```typescript
// Props
let { class: className = '', adapter }: Props = $props();

// State
let count = $state(0);

// Computed
const doubled = $derived(count * 2);

// Effects
$effect(() => {
  console.log('Count:', count);
  return () => cleanup();
});

// SuperForms
const { form, errors, enhance } = $derived(
  superForm(data, {
    SPA: true,
    validators: zodClient(schema),
    onUpdate: async ({ form }) => {
      /* handle submit */
    },
  }),
);
```

## Import Order

1. Node.js built-ins
2. External libraries (with `svelte/**` first)
3. SvelteKit imports (`$app/**`, `$types`)
4. Internal imports (`$lib/**`)
5. Component imports (`$components/**/*.svelte`)
6. Relative imports (`./`, `../`)

## Workflow

1. **Always run linting**: Execute `pnpm lint` after making changes
2. **Type checking**: Run `pnpm check` to verify TypeScript compliance
3. **Test execution**: Run appropriate test suites based on changes
4. **Follow patterns**: Use existing component patterns and utility functions
5. **Design system**: Prefer Holocene components over custom implementations
6. **Accessibility**: Ensure proper ARIA attributes and semantic HTML

## Code Generation

- **No comments**: Don't add code comments unless explicitly requested
- **Type safety**: Always provide proper TypeScript types
- **Component reuse**: Leverage existing components and utilities
- **Test coverage**: Write tests for new utilities and business logic
- **Import organization**: Follow the established import order

## Error Handling

- **Validation**: Use Zod for runtime type validation
- **Error boundaries**: Implement proper error boundaries for components
- **Network errors**: Handle API failures gracefully
- **User feedback**: Provide clear error messages and loading states

## Naming

- **Files**: kebab-case (`workflow-status.svelte`)
- **Components**: PascalCase in imports, kebab-case for files
- **Functions**: camelCase
- **Types**: PascalCase
- **Use** `import type` for type-only imports
