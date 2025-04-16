### Accordion
A vertically stacked set of interactive headings that each reveal a section of content.
`pnpm dlx shadcn@latest add accordion`
[Accordion docs](https://ui.shadcn.com/docs/components/accordion)

#### Variants
There are no variants for this component, but behavior can be controlled via props like `type` (`"single"` or `"multiple"`).

#### Syntax
```tsx
import { Accordion, AccordionContent, AccordionItem, AccordionTrigger } from "@/components/ui/accordion"

<Accordion type="single" collapsible>
  <AccordionItem value="item-1">
    <AccordionTrigger>Is it accessible?</AccordionTrigger>
    <AccordionContent>
      Yes. It adheres to the WAI-ARIA design pattern.
    </AccordionContent>
  </AccordionItem>
  <AccordionItem value="item-2">
    <AccordionTrigger>Is it styled?</AccordionTrigger>
    <AccordionContent>
      Yes. It comes with default styles that matches the other components' aesthetic.
    </AccordionContent>
  </AccordionItem>
</Accordion>
```

#### Rules
- The `value` prop on `AccordionItem` must be unique for each item within an `Accordion`.
- Use `type="single"` to allow only one item to be open at a time.
- Use `type="multiple"` to allow multiple items to be open simultaneously.
- Add the `collapsible` prop to `Accordion` (when `type="single"`) to allow closing the currently open item.

---

### Alert
Displays a short, important message in a way that attracts the user's attention without interrupting their task.
`pnpm dlx shadcn@latest add alert`
[Alert docs](https://ui.shadcn.com/docs/components/alert)

#### Variants
**Alert**
- **variant**: `"default"`, `"destructive"`

#### Syntax
```tsx
import { Alert, AlertDescription, AlertTitle } from "@/components/ui/alert"
import { Terminal } from "lucide-react" // Example icon

<Alert>
  <Terminal className="h-4 w-4" />
  <AlertTitle>Heads up!</AlertTitle>
  <AlertDescription>
    You can add components to your app using the cli.
  </AlertDescription>
</Alert>

<Alert variant="destructive">
  <Terminal className="h-4 w-4" />
  <AlertTitle>Error</AlertTitle>
  <AlertDescription>
    Your session has expired. Please log in again.
  </AlertDescription>
</Alert>
```

#### Rules
- Icons are optional but recommended for clarity, often placed before `AlertTitle`. Use a library like `lucide-react`.

---

### Alert Dialog
A modal dialog that interrupts the user with important content and expects a response.
`pnpm dlx shadcn@latest add alert-dialog`
[Alert Dialog docs](https://ui.shadcn.com/docs/components/alert-dialog)

#### Variants
There are no variants for the dialog itself, but nested `Button` components can have variants.

#### Syntax
```tsx
import {
  AlertDialog,
  AlertDialogAction,
  AlertDialogCancel,
  AlertDialogContent,
  AlertDialogDescription,
  AlertDialogFooter,
  AlertDialogHeader,
  AlertDialogTitle,
  AlertDialogTrigger,
} from "@/components/ui/alert-dialog"
import { Button } from "@/components/ui/button" // Often used for the trigger

<AlertDialog>
  <AlertDialogTrigger asChild>
    <Button variant="outline">Show Dialog</Button>
  </AlertDialogTrigger>
  <AlertDialogContent>
    <AlertDialogHeader>
      <AlertDialogTitle>Are you absolutely sure?</AlertDialogTitle>
      <AlertDialogDescription>
        This action cannot be undone. This will permanently delete your
        account and remove your data from our servers.
      </AlertDialogDescription>
    </AlertDialogHeader>
    <AlertDialogFooter>
      <AlertDialogCancel>Cancel</AlertDialogCancel>
      <AlertDialogAction>Continue</AlertDialogAction>
    </AlertDialogFooter>
  </AlertDialogContent>
</AlertDialog>
```

#### Rules
- Use `AlertDialog` for critical confirmations that interrupt the user flow (e.g., deletion confirmation). For less critical modals, use `Dialog`.
- `AlertDialogCancel` typically closes the dialog.
- `AlertDialogAction` typically performs the confirmed action and may also close the dialog.
- Use `asChild` on `AlertDialogTrigger` when nesting a custom component like `Button` to avoid rendering extra DOM elements.

---

### Aspect Ratio
Displays content within a desired ratio.
`pnpm dlx shadcn@latest add aspect-ratio`
[Aspect Ratio docs](https://ui.shadcn.com/docs/components/aspect-ratio)

#### Variants
There are no variants for this component. The ratio is controlled via the `ratio` prop.

#### Syntax
```tsx
import { AspectRatio } from "@/components/ui/aspect-ratio"

<div className="w-[450px]"> {/* Example container */}
  <AspectRatio ratio={16 / 9} className="bg-muted">
    <img
      src="https://images.unsplash.com/photo-1588345921523-c2dcdb7f1dcd?w=800&dpr=2&q=80"
      alt="Photo by Drew Beamer"
      className="rounded-md object-cover w-full h-full"
    />
  </AspectRatio>
</div>```

#### Rules
- Requires a child element which will be constrained to the specified aspect ratio.
- Often used for images or video embeds.
- The parent container typically needs a defined width or height for the aspect ratio to work correctly.

---

### Avatar
An image element with a fallback for representing users or entities.
`pnpm dlx shadcn@latest add avatar`
[Avatar docs](https://ui.shadcn.com/docs/components/avatar)

#### Variants
There are no variants for this component. Size is controlled via standard CSS classes (`h-`, `w-`).

#### Syntax
```tsx
import { Avatar, AvatarFallback, AvatarImage } from "@/components/ui/avatar"

<Avatar>
  <AvatarImage src="https://github.com/shadcn.png" alt="@shadcn" />
  <AvatarFallback>CN</AvatarFallback>
</Avatar>```

#### Rules
- `AvatarImage` displays the image. If the image fails to load or `src` is not provided, `AvatarFallback` is displayed.
- `AvatarFallback` content is typically initials or a placeholder icon.
- Add size classes (e.g., `h-10 w-10`) directly to the `Avatar` component.

---

### Badge
Displays small pieces of information, often used for categories or statuses.
`pnpm dlx shadcn@latest add badge`
[Badge docs](https://ui.shadcn.com/docs/components/badge)

#### Variants
**Badge**
- **variant**: `"default"`, `"secondary"`, `"destructive"`, `"outline"`

#### Syntax
```tsx
import { Badge } from "@/components/ui/badge"

<div>
  <Badge>Default</Badge>
  <Badge variant="secondary">Secondary</Badge>
  <Badge variant="outline">Outline</Badge>
  <Badge variant="destructive">Destructive</Badge>
</div>
```

#### Rules
- Badges are inline elements by default.

---

### Button
Displays a button or a link that looks like a button.
`pnpm dlx shadcn@latest add button`
[Button docs](https://ui.shadcn.com/docs/components/button)

#### Variants
**Button**
- **variant**: `"default"`, `"destructive"`, `"outline"`, `"secondary"`, `"ghost"`, `"link"`
- **size**: `"default"`, `"sm"`, `"lg"`, `"icon"`

#### Syntax
```tsx
import { Button } from "@/components/ui/button"
import { Mail } from "lucide-react" // Example icon

<div>
  <Button>Default</Button>
  <Button variant="destructive">Destructive</Button>
  <Button variant="outline">Outline</Button>
  <Button variant="secondary">Secondary</Button>
  <Button variant="ghost">Ghost</Button>
  <Button variant="link">Link</Button>

  <Button size="lg">Large</Button>
  <Button size="sm">Small</Button>

  <Button variant="outline" size="icon">
    <Mail className="h-4 w-4" /> {/* Use size="icon" for icon-only buttons */}
  </Button>

  <Button>
    <Mail className="mr-2 h-4 w-4" /> Login with Email {/* Icon with text */}
  </Button>

  <Button disabled>Disabled</Button>

  <Button asChild> {/* Use asChild to render a Link component styled as a button */}
    <a href="/login">Login</a>
  </Button>
</div>
```

#### Rules
- Use `size="icon"` for buttons containing only an icon, ensuring appropriate padding and square dimensions.
- Use `asChild` prop when you want the button's styles applied to a child component (like a Next.js `<Link>` or a simple `<a>` tag) instead of rendering a `button` element.

---

### Calendar
Displays a calendar for date selection. Usually used within components like DatePicker or Popover.
`pnpm dlx shadcn@latest add calendar`
[Calendar docs](https://ui.shadcn.com/docs/components/calendar)

#### Variants
There are no direct variants, but appearance and behavior are controlled via props from `react-day-picker`.

#### Syntax
```tsx
import * as React from "react"
import { Calendar } from "@/components/ui/calendar"

export function CalendarDemo() {
  const [date, setDate] = React.useState<Date | undefined>(new Date())

  return (
    <Calendar
      mode="single"
      selected={date}
      onSelect={setDate}
      className="rounded-md border"
    />
  )
}
```

#### Rules
- This component is based on `react-day-picker`. Refer to its documentation for advanced customization (modes like `multiple`, `range`, disabling dates, etc.).
- State management (like the selected date) needs to be handled in the parent component.
- It's often combined with `Popover` to create a `DatePicker`.

---

### Card
Displays content and actions about a single subject.
`pnpm dlx shadcn@latest add card`
[Card docs](https://ui.shadcn.com/docs/components/card)

#### Variants
There are no variants for this component.

#### Syntax
```tsx
import { Card, CardContent, CardDescription, CardFooter, CardHeader, CardTitle } from "@/components/ui/card"
import { Button } from "@/components/ui/button" // Example content

<Card className="w-[350px]"> {/* Example width */}
  <CardHeader>
    <CardTitle>Create project</CardTitle>
    <CardDescription>Deploy your new project in one-click.</CardDescription>
  </CardHeader>
  <CardContent>
    {/* Form elements or other content */}
    <p>Card Content Area</p>
  </CardContent>
  <CardFooter className="flex justify-between">
    <Button variant="outline">Cancel</Button>
    <Button>Deploy</Button>
  </CardFooter>
</Card>
```

#### Rules
- `CardHeader`, `CardContent`, and `CardFooter` are optional but provide standard structure and padding.
- `CardTitle` and `CardDescription` are typically used within `CardHeader`.

---

### Checkbox
A control that allows the user to toggle between checked and unchecked states.
`pnpm dlx shadcn@latest add checkbox`
[Checkbox docs](https://ui.shadcn.com/docs/components/checkbox)

#### Variants
There are no variants for this component.

#### Syntax
```tsx
import * as React from "react"
import { Checkbox } from "@/components/ui/checkbox"
import { Label } from "@/components/ui/label" // Often used with Label

export function CheckboxDemo() {
  const [isChecked, setIsChecked] = React.useState(false)

  return (
    <div className="flex items-center space-x-2">
      <Checkbox
        id="terms"
        checked={isChecked}
        onCheckedChange={(checked) => setIsChecked(checked as boolean)}
      />
      <Label htmlFor="terms">Accept terms and conditions</Label>
    </div>
  )
}
```

#### Rules
- Control the state (`checked`) and handle changes (`onCheckedChange`) in the parent component.
- Often used with a `Label` component for accessibility. Ensure the `htmlFor` prop on `Label` matches the `id` prop on `Checkbox`.
- The `onCheckedChange` callback receives `true`, `false`, or `"indeterminate"`. Handle accordingly.

---

### Collapsible
An interactive component which expands/collapses a content area.
`pnpm dlx shadcn@latest add collapsible`
[Collapsible docs](https://ui.shadcn.com/docs/components/collapsible)

#### Variants
There are no variants for this component. Open state is controlled via `open` and `onOpenChange` props or internally.

#### Syntax
```tsx
import * as React from "react"
import { ChevronsUpDown } from "lucide-react" // Example icon

import { Button } from "@/components/ui/button"
import {
  Collapsible,
  CollapsibleContent,
  CollapsibleTrigger,
} from "@/components/ui/collapsible"

export function CollapsibleDemo() {
  const [isOpen, setIsOpen] = React.useState(false)

  return (
    <Collapsible
      open={isOpen}
      onOpenChange={setIsOpen}
      className="w-[350px] space-y-2"
    >
      <div className="flex items-center justify-between space-x-4 px-4">
        <h4 className="text-sm font-semibold">
          @peduarte starred 3 repositories
        </h4>
        <CollapsibleTrigger asChild>
          <Button variant="ghost" size="sm" className="w-9 p-0">
            <ChevronsUpDown className="h-4 w-4" />
            <span className="sr-only">Toggle</span>
          </Button>
        </CollapsibleTrigger>
      </div>
      <div className="rounded-md border px-4 py-3 font-mono text-sm">
        @radix-ui/primitives
      </div>
      <CollapsibleContent className="space-y-2">
        <div className="rounded-md border px-4 py-3 font-mono text-sm">
          @radix-ui/colors
        </div>
        <div className="rounded-md border px-4 py-3 font-mono text-sm">
          @stitches/react
        </div>
      </CollapsibleContent>
    </Collapsible>
  )
}
```

#### Rules
- `CollapsibleTrigger` toggles the open/closed state.
- `CollapsibleContent` contains the content that is shown or hidden.
- State can be controlled (`open`, `onOpenChange`) or uncontrolled (default behavior).

---

### Combobox
Autocomplete input and command palette with a list of suggestions. Built using Popover, Command, and Button.
`pnpm dlx shadcn@latest add combobox popover command button`
[Combobox docs](https://ui.shadcn.com/docs/components/combobox)

#### Variants
No specific variants for the Combobox pattern itself, but uses `Button` variants.

#### Syntax
```tsx
"use client" // Required for state and event handlers

import * as React from "react"
import { Check, ChevronsUpDown } from "lucide-react"

import { cn } from "@/lib/utils" // Assumes utils file exists
import { Button } from "@/components/ui/button"
import {
  Command,
  CommandEmpty,
  CommandGroup,
  CommandInput,
  CommandItem,
  CommandList, // Added CommandList
} from "@/components/ui/command"
import {
  Popover,
  PopoverContent,
  PopoverTrigger,
} from "@/components/ui/popover"

const frameworks = [
  { value: "next.js", label: "Next.js" },
  { value: "sveltekit", label: "SvelteKit" },
  // ... other frameworks
]

export function ComboboxDemo() {
  const [open, setOpen] = React.useState(false)
  const [value, setValue] = React.useState("")

  return (
    <Popover open={open} onOpenChange={setOpen}>
      <PopoverTrigger asChild>
        <Button
          variant="outline"
          role="combobox"
          aria-expanded={open}
          className="w-[200px] justify-between"
        >
          {value
            ? frameworks.find((framework) => framework.value === value)?.label
            : "Select framework..."}
          <ChevronsUpDown className="ml-2 h-4 w-4 shrink-0 opacity-50" />
        </Button>
      </PopoverTrigger>
      <PopoverContent className="w-[200px] p-0">
        <Command>
          <CommandInput placeholder="Search framework..." />
          <CommandList> {/* Wrap items in CommandList */}
            <CommandEmpty>No framework found.</CommandEmpty>
            <CommandGroup>
              {frameworks.map((framework) => (
                <CommandItem
                  key={framework.value}
                  value={framework.value} // Ensure value is set for filtering/selection
                  onSelect={(currentValue) => {
                    setValue(currentValue === value ? "" : currentValue)
                    setOpen(false)
                  }}
                >
                  <Check
                    className={cn(
                      "mr-2 h-4 w-4",
                      value === framework.value ? "opacity-100" : "opacity-0"
                    )}
                  />
                  {framework.label}
                </CommandItem>
              ))}
            </CommandGroup>
          </CommandList>
        </Command>
      </PopoverContent>
    </Popover>
  )
}
```

#### Rules
- This is a composite component pattern, not a single installable component named 'combobox'. It requires `Popover`, `Command`, and `Button`.
- Requires client-side state management (`useState`) for open state and selected value. Mark parent component with `"use client"`.
- The `CommandItem`'s `onSelect` handler receives the `value` prop of the selected item. Use this to update state.
- Wrap `CommandGroup` and `CommandItem` within `CommandList` for proper scrolling and structure, especially with `CommandInput`.

---

### Command
Fast, composable command menu. Often used within a Dialog or Popover.
`pnpm dlx shadcn@latest add command dialog` (Dialog is often used with it)
[Command docs](https://ui.shadcn.com/docs/components/command)

#### Variants
There are no variants for this component.

#### Syntax
```tsx
import {
  Command,
  CommandDialog, // If used within a dialog
  CommandEmpty,
  CommandGroup,
  CommandInput,
  CommandItem,
  CommandList,
  CommandSeparator,
  CommandShortcut,
} from "@/components/ui/command"
import { useEffect, useState } from "react" // For dialog usage example

export function CommandMenu() {
    // Example state for Dialog usage
    const [open, setOpen] = useState(false)

    // Example: Toggle the menu with K key
    useEffect(() => {
        const down = (e: KeyboardEvent) => {
            if (e.key === "k" && (e.metaKey || e.ctrlKey)) {
            e.preventDefault()
            setOpen((open) => !open)
            }
        }
        document.addEventListener("keydown", down)
        return () => document.removeEventListener("keydown", down)
    }, [])


  return (
    <>
      {/* Example Trigger (could be anything) */}
      <p className="text-sm text-muted-foreground">
          Press{" "}
          <kbd className="pointer-events-none inline-flex h-5 select-none items-center gap-1 rounded border bg-muted px-1.5 font-mono text-[10px] font-medium text-muted-foreground opacity-100">
          <span className="text-xs">⌘</span>K
          </kbd>
      </p>

      {/* Example using CommandDialog */}
      <CommandDialog open={open} onOpenChange={setOpen}>
          <CommandInput placeholder="Type a command or search..." />
          <CommandList>
              <CommandEmpty>No results found.</CommandEmpty>
              <CommandGroup heading="Suggestions">
                  <CommandItem>Calendar</CommandItem>
                  <CommandItem>Search Emoji</CommandItem>
                  <CommandItem>Calculator</CommandItem>
              </CommandGroup>
              <CommandSeparator />
              <CommandGroup heading="Settings">
                  <CommandItem>Profile</CommandItem>
                  <CommandItem>Billing</CommandItem>
                  <CommandItem>Settings</CommandItem>
              </CommandGroup>
          </CommandList>
      </CommandDialog>

      {/* Example of standalone Command */}
      {/* <Command className="rounded-lg border shadow-md">
          <CommandInput placeholder="Type a command or search..." />
          <CommandList>
              <CommandEmpty>No results found.</CommandEmpty>
              <CommandGroup heading="Suggestions">...</CommandGroup>
          </CommandList>
      </Command> */}
    </>
  )
}
```

#### Rules
- `CommandInput` provides the search functionality.
- `CommandList` wraps the results and handles scrolling.
- `CommandEmpty` displays when there are no matching results.
- `CommandGroup` organizes items under headings.
- `CommandItem` represents a selectable command.
- `CommandSeparator` visually separates groups.
- `CommandShortcut` displays keyboard shortcuts associated with an item (usually floated right).
- Often requires client components (`"use client"`) for interactions and state.

---

### Context Menu
Displays a menu to the user — such as a set of actions — when they right-click.
`pnpm dlx shadcn@latest add context-menu`
[Context Menu docs](https://ui.shadcn.com/docs/components/context-menu)

#### Variants
There are no variants for the menu itself, but menu items can be styled or include submenus.

#### Syntax
```tsx
import {
  ContextMenu,
  ContextMenuCheckboxItem,
  ContextMenuContent,
  ContextMenuItem,
  ContextMenuLabel,
  ContextMenuRadioGroup,
  ContextMenuRadioItem,
  ContextMenuSeparator,
  ContextMenuShortcut,
  ContextMenuSub,
  ContextMenuSubContent,
  ContextMenuSubTrigger,
  ContextMenuTrigger,
} from "@/components/ui/context-menu"

<ContextMenu>
  <ContextMenuTrigger className="flex h-[150px] w-[300px] items-center justify-center rounded-md border border-dashed text-sm">
    Right-click here
  </ContextMenuTrigger>
  <ContextMenuContent className="w-64">
    <ContextMenuItem inset>
      Back
      <ContextMenuShortcut>⌘[</ContextMenuShortcut>
    </ContextMenuItem>
    <ContextMenuItem inset disabled>
      Forward
      <ContextMenuShortcut>⌘]</ContextMenuShortcut>
    </ContextMenuItem>
    {/* ... other items ... */}
    <ContextMenuSeparator />
    <ContextMenuCheckboxItem checked>
      Show Bookmarks Bar
      <ContextMenuShortcut>⌘⇧B</ContextMenuShortcut>
    </ContextMenuCheckboxItem>
    {/* ... other items ... */}
    <ContextMenuSeparator />
     <ContextMenuSub>
        <ContextMenuSubTrigger inset>More Tools</ContextMenuSubTrigger>
        <ContextMenuSubContent className="w-48">
          <ContextMenuItem>Save Page As...</ContextMenuItem>
          <ContextMenuItem>Create Shortcut...</ContextMenuItem>
        </ContextMenuSubContent>
      </ContextMenuSub>
     {/* ... other items ... */}
  </ContextMenuContent>
</ContextMenu>
```

#### Rules
- Wrap the element that should trigger the menu on right-click with `ContextMenuTrigger`.
- `ContextMenuContent` holds the menu items.
- Various item types are available: `ContextMenuItem`, `ContextMenuCheckboxItem`, `ContextMenuRadioItem` (within `ContextMenuRadioGroup`), `ContextMenuLabel`, `ContextMenuSeparator`.
- Submenus can be created using `ContextMenuSub`, `ContextMenuSubTrigger`, and `ContextMenuSubContent`.
- The `inset` prop on items adds padding for alignment, useful if some items have icons/checkboxes and others don't.

---

### Data Table
A responsive table component built using TanStack Table V8. This is a complex component pattern.
`pnpm dlx shadcn@latest add table button checkbox dropdown-menu`
`pnpm install @tanstack/react-table`
[Data Table docs](https://ui.shadcn.com/docs/components/data-table)

#### Variants
No specific variants for the table pattern itself, but uses `Button`, `Checkbox`, `DropdownMenu`, and base `Table` components which may have variants.

#### Syntax
```tsx
// This is a simplified conceptual structure.
// Refer to the official docs for the full implementation,
// including column definitions, state management, and handlers.

"use client"

import * as React from "react"
import {
  ColumnDef,
  SortingState,
  flexRender,
  getCoreRowModel,
  getSortedRowModel,
  useReactTable,
  // ... other imports like getPaginationRowModel, getFilteredRowModel etc.
} from "@tanstack/react-table"

import {
  Table,
  TableBody,
  TableCell,
  TableHead,
  TableHeader,
  TableRow,
} from "@/components/ui/table"
import { Button } from "@/components/ui/button"
import { Input } from "@/components/ui/input"
// ... other necessary shadcn imports (Checkbox, DropdownMenu etc.)

// Define your data type
interface Payment {
  id: string
  amount: number
  status: "pending" | "processing" | "success" | "failed"
  email: string
}

// Define columns (see docs for details on column helpers, headers, cells)
export const columns: ColumnDef<Payment>[] = [
  // Example column definition (needs Checkbox, DropdownMenu for full functionality)
  {
    accessorKey: "status",
    header: "Status",
  },
  {
    accessorKey: "email",
    header: "Email",
  },
  {
    accessorKey: "amount",
    header: "Amount",
  },
  // ... Add actions column with DropdownMenu if needed
]

export function DataTableDemo({ data }: { data: Payment[] }) {
  const [sorting, setSorting] = React.useState<SortingState>([])
  // ... Add state for filtering, pagination, row selection etc.

  const table = useReactTable({
    data,
    columns,
    getCoreRowModel: getCoreRowModel(),
    // ... Add other model getters: getPaginationRowModel(), getSortedRowModel(), getFilteredRowModel()
    onSortingChange: setSorting,
    // ... Add other state handlers
    state: {
      sorting,
      // ... other states
    },
  })

  return (
    <div>
      {/* Add Input for filtering, Dropdown for column visibility etc. here */}
       <div className="rounded-md border">
         <Table>
           <TableHeader>
             {table.getHeaderGroups().map((headerGroup) => (
               <TableRow key={headerGroup.id}>
                 {headerGroup.headers.map((header) => {
                   return (
                     <TableHead key={header.id}>
                       {header.isPlaceholder
                         ? null
                         : flexRender(
                             header.column.columnDef.header,
                             header.getContext()
                           )}
                     </TableHead>
                   )
                 })}
               </TableRow>
             ))}
           </TableHeader>
           <TableBody>
             {table.getRowModel().rows?.length ? (
               table.getRowModel().rows.map((row) => (
                 <TableRow
                   key={row.id}
                   data-state={row.getIsSelected() && "selected"}
                 >
                   {row.getVisibleCells().map((cell) => (
                     <TableCell key={cell.id}>
                       {flexRender(cell.column.columnDef.cell, cell.getContext())}
                     </TableCell>
                   ))}
                 </TableRow>
               ))
             ) : (
               <TableRow>
                 <TableCell colSpan={columns.length} className="h-24 text-center">
                   No results.
                 </TableCell>
               </TableRow>
             )}
           </TableBody>
         </Table>
       </div>
       {/* Add Pagination controls here */}
    </div>
  )
}
```

#### Rules
- Requires installation of `@tanstack/react-table`.
- Requires significant setup: defining data structure, column definitions (`ColumnDef[]`), and initializing the table instance using `useReactTable`.
- State management (sorting, filtering, pagination, row selection) is handled via `useState` and passed to `useReactTable`.
- Uses shadcn `Table` components for rendering. `flexRender` from `@tanstack/react-table` is used to render header and cell content.
- This is a complex pattern; refer extensively to the official Shadcn UI Data Table documentation and examples. Requires `"use client"`.

---

### Date Picker
A component for selecting dates, typically combining Calendar, Popover, and Button.
`pnpm dlx shadcn@latest add date-picker button popover calendar`
[Date Picker docs](https://ui.shadcn.com/docs/components/date-picker)

#### Variants
No specific variants for the Date Picker pattern, but uses `Button` variants.

#### Syntax
```tsx
"use client" // Required for state and interaction

import * as React from "react"
import { format } from "date-fns"
import { Calendar as CalendarIcon } from "lucide-react"

import { cn } from "@/lib/utils" // Assumes utils file exists
import { Button } from "@/components/ui/button"
import { Calendar } from "@/components/ui/calendar"
import {
  Popover,
  PopoverContent,
  PopoverTrigger,
} from "@/components/ui/popover"

export function DatePickerDemo() {
  const [date, setDate] = React.useState<Date>()

  return (
    <Popover>
      <PopoverTrigger asChild>
        <Button
          variant={"outline"}
          className={cn(
            "w-[280px] justify-start text-left font-normal",
            !date && "text-muted-foreground"
          )}
        >
          <CalendarIcon className="mr-2 h-4 w-4" />
          {date ? format(date, "PPP") : <span>Pick a date</span>}
        </Button>
      </PopoverTrigger>
      <PopoverContent className="w-auto p-0">
        <Calendar
          mode="single"
          selected={date}
          onSelect={setDate}
          initialFocus
        />
      </PopoverContent>
    </Popover>
  )
}
```

#### Rules
- This is a composite pattern requiring `Button`, `Popover`, and `Calendar`.
- Requires `date-fns` (or similar library) for formatting dates. Install it: `pnpm add date-fns`.
- Requires client-side state (`useState`) to manage the selected date. Mark parent component with `"use client"`.
- The `Calendar` component's `onSelect` updates the state.
- The `Button` displays the selected date or a placeholder.

---

### Dialog
A window overlaid on either the primary window or another dialog window, rendering the content underneath inert.
`pnpm dlx shadcn@latest add dialog`
[Dialog docs](https://ui.shadcn.com/docs/components/dialog)

#### Variants
There are no variants for the dialog itself, but nested components like `Button` can have variants.

#### Syntax
```tsx
import {
  Dialog,
  DialogContent,
  DialogDescription,
  DialogFooter,
  DialogHeader,
  DialogTitle,
  DialogTrigger,
  DialogClose, // Optional: For specific close buttons inside content
} from "@/components/ui/dialog"
import { Button } from "@/components/ui/button" // Often used for the trigger and actions
import { Input } from "@/components/ui/input" // Example content
import { Label } from "@/components/ui/label" // Example content

<Dialog>
  <DialogTrigger asChild>
    <Button variant="outline">Edit Profile</Button>
  </DialogTrigger>
  <DialogContent className="sm:max-w-[425px]">
    <DialogHeader>
      <DialogTitle>Edit profile</DialogTitle>
      <DialogDescription>
        Make changes to your profile here. Click save when you're done.
      </DialogDescription>
    </DialogHeader>
    <div className="grid gap-4 py-4">
      {/* Example form content */}
      <div className="grid grid-cols-4 items-center gap-4">
        <Label htmlFor="name" className="text-right">
          Name
        </Label>
        <Input id="name" value="Pedro Duarte" className="col-span-3" />
      </div>
      <div className="grid grid-cols-4 items-center gap-4">
        <Label htmlFor="username" className="text-right">
          Username
        </Label>
        <Input id="username" value="@peduarte" className="col-span-3" />
      </div>
    </div>
    <DialogFooter>
        {/* Example: DialogClose can wrap a button to handle closing */}
      {/* <DialogClose asChild> */}
          <Button type="submit">Save changes</Button>
      {/* </DialogClose> */}
    </DialogFooter>
  </DialogContent>
</Dialog>
```

#### Rules
- Use `Dialog` for modals that don't require immediate, blocking confirmation (unlike `AlertDialog`).
- `DialogTrigger` opens the modal. Use `asChild` when nesting a custom component like `Button`.
- `DialogContent` contains the modal's content.
- `DialogHeader`, `DialogTitle`, `DialogDescription`, `DialogFooter` provide structure.
- Closing the dialog usually happens by clicking outside the `DialogContent`, pressing `Escape`, or clicking an element wrapped in `DialogClose`.

---

### Dropdown Menu
Displays a menu to the user — such as a list of actions or functions — triggered by a button.
`pnpm dlx shadcn@latest add dropdown-menu`
[Dropdown Menu docs](https://ui.shadcn.com/docs/components/dropdown-menu)

#### Variants
There are no variants for the menu itself, but nested components like `Button` (often used as the trigger) can have variants.

#### Syntax
```tsx
import {
  DropdownMenu,
  DropdownMenuContent,
  DropdownMenuGroup,
  DropdownMenuItem,
  DropdownMenuLabel,
  DropdownMenuPortal,
  DropdownMenuSeparator,
  DropdownMenuShortcut,
  DropdownMenuSub,
  DropdownMenuSubContent,
  DropdownMenuSubTrigger,
  DropdownMenuCheckboxItem, // For checkbox items
  DropdownMenuRadioGroup, // For radio groups
  DropdownMenuRadioItem, // For radio items
  DropdownMenuTrigger,
} from "@/components/ui/dropdown-menu"
import { Button } from "@/components/ui/button" // Often used as trigger
import * as React from "react" // For stateful items like checkbox/radio

export function DropdownMenuDemo() {
    // Example state for Checkbox items
    const [showStatusBar, setShowStatusBar] = React.useState(true)
    // Example state for Radio items
    const [position, setPosition] = React.useState("bottom")

    return (
        <DropdownMenu>
        <DropdownMenuTrigger asChild>
            <Button variant="outline">Open Menu</Button>
        </DropdownMenuTrigger>
        <DropdownMenuContent className="w-56">
            <DropdownMenuLabel>My Account</DropdownMenuLabel>
            <DropdownMenuSeparator />
            <DropdownMenuGroup>
            <DropdownMenuItem>
                Profile
                <DropdownMenuShortcut>⇧⌘P</DropdownMenuShortcut>
            </DropdownMenuItem>
            <DropdownMenuItem>
                Billing
                <DropdownMenuShortcut>⌘B</DropdownMenuShortcut>
            </DropdownMenuItem>
            {/* ... more items ... */}
            </DropdownMenuGroup>
            <DropdownMenuSeparator />
            <DropdownMenuGroup>
                 <DropdownMenuSub>
                    <DropdownMenuSubTrigger>Invite users</DropdownMenuSubTrigger>
                    <DropdownMenuPortal>
                        <DropdownMenuSubContent>
                        <DropdownMenuItem>Email</DropdownMenuItem>
                        <DropdownMenuItem>Message</DropdownMenuItem>
                        <DropdownMenuSeparator />
                        <DropdownMenuItem>More...</DropdownMenuItem>
                        </DropdownMenuSubContent>
                    </DropdownMenuPortal>
                </DropdownMenuSub>
                {/* ... more items ... */}
            </DropdownMenuGroup>
            <DropdownMenuSeparator />
            <DropdownMenuCheckboxItem
                checked={showStatusBar}
                onCheckedChange={setShowStatusBar}
            >
                Status Bar
            </DropdownMenuCheckboxItem>
            <DropdownMenuSeparator />
            <DropdownMenuRadioGroup value={position} onValueChange={setPosition}>
                <DropdownMenuLabel>Panel Position</DropdownMenuLabel>
                <DropdownMenuSeparator />
                <DropdownMenuRadioItem value="top">Top</DropdownMenuRadioItem>
                <DropdownMenuRadioItem value="bottom">Bottom</DropdownMenuRadioItem>
                <DropdownMenuRadioItem value="right">Right</DropdownMenuRadioItem>
            </DropdownMenuRadioGroup>
            <DropdownMenuSeparator />
            <DropdownMenuItem disabled>
                API Tokens
                <DropdownMenuShortcut>⌘T</DropdownMenuShortcut>
            </DropdownMenuItem>
            {/* ... more items ... */}
        </DropdownMenuContent>
        </DropdownMenu>
    )
}
```

#### Rules
- Wrap the trigger element (often a `Button`) with `DropdownMenuTrigger`. Use `asChild`.
- `DropdownMenuContent` holds the menu items.
- Various item types are available: `DropdownMenuItem`, `DropdownMenuCheckboxItem`, `DropdownMenuRadioItem` (within `DropdownMenuRadioGroup`), `DropdownMenuLabel`, `DropdownMenuSeparator`.
- Requires `"use client"` and `React.useState` if using stateful items like `DropdownMenuCheckboxItem` or `DropdownMenuRadioGroup`.
- Submenus are created with `DropdownMenuSub`, `DropdownMenuSubTrigger`, `DropdownMenuSubContent`, and `DropdownMenuPortal`.
- `DropdownMenuGroup` can be used to group related items visually (often separated by `DropdownMenuSeparator`).

---

### Form
Provides form building capabilities using React Hook Form and Zod. Includes components for fields, labels, messages, etc.
`pnpm dlx shadcn@latest add form button label input` (and others depending on fields used)
`pnpm install react-hook-form zod @hookform/resolvers`
[Form docs](https://ui.shadcn.com/docs/components/form)

#### Variants
No specific variants for the Form component itself, but underlying input components (`Input`, `Select`, `Checkbox`, etc.) may have their own variants.

#### Syntax
```tsx
"use client" // Required for hooks and handlers

import { zodResolver } from "@hookform/resolvers/zod"
import { useForm } from "react-hook-form"
import * as z from "zod"

import { Button } from "@/components/ui/button"
import {
  Form,
  FormControl,
  FormDescription,
  FormField,
  FormItem,
  FormLabel,
  FormMessage,
} from "@/components/ui/form"
import { Input } from "@/components/ui/input"
import { toast } from "@/components/ui/use-toast" // Assuming Toast is set up

// Define your form schema using Zod
const formSchema = z.object({
  username: z.string().min(2, {
    message: "Username must be at least 2 characters.",
  }),
})

export function ProfileForm() {
  // 1. Define your form.
  const form = useForm<z.infer<typeof formSchema>>({
    resolver: zodResolver(formSchema),
    defaultValues: {
      username: "",
    },
  })

  // 2. Define a submit handler.
  function onSubmit(values: z.infer<typeof formSchema>) {
    // Do something with the form values.
    // ✅ This will be type-safe and validated.
    console.log(values)
    toast({ // Example using toast
        title: "You submitted the following values:",
        description: (
            <pre className="mt-2 w-[340px] rounded-md bg-slate-950 p-4">
            <code className="text-white">{JSON.stringify(values, null, 2)}</code>
            </pre>
        ),
    })
  }

  return (
    <Form {...form}>
      <form onSubmit={form.handleSubmit(onSubmit)} className="space-y-8">
        <FormField
          control={form.control}
          name="username" // Must match a key in your Zod schema
          render={({ field }) => (
            <FormItem>
              <FormLabel>Username</FormLabel>
              <FormControl>
                <Input placeholder="shadcn" {...field} />
              </FormControl>
              <FormDescription>
                This is your public display name.
              </FormDescription>
              <FormMessage /> {/* Displays validation errors */}
            </FormItem>
          )}
        />
        {/* Add more FormField elements for other inputs */}
        <Button type="submit">Submit</Button>
      </form>
    </Form>
  )
}
```

#### Rules
- Requires installation of `react-hook-form`, `zod`, and `@hookform/resolvers`.
- Requires `"use client"`.
- Define a validation schema using Zod (`z.object({...})`).
- Initialize the form using `useForm` from `react-hook-form`, passing the schema via `zodResolver`.
- Wrap your form elements in the `Form` component provided by shadcn, spreading the form instance (`{...form}`).
- Use the native `form` element and handle submission with `form.handleSubmit(yourSubmitFunction)`.
- Each form input should be wrapped in a `FormField` component.
    - `control` prop must be `form.control`.
    - `name` prop must match a key in your Zod schema.
    - The `render` prop receives `field` which should be spread onto your input component (`{...field}`). This connects the input to `react-hook-form`.
- Use `FormItem`, `FormLabel`, `FormControl`, `FormDescription`, and `FormMessage` within `FormField` for structure, accessibility, and displaying validation messages.

---

### Hover Card
For sighted users to preview content available behind a link.
`pnpm dlx shadcn@latest add hover-card`
[Hover Card docs](https://ui.shadcn.com/docs/components/hover-card)

#### Variants
There are no variants for this component.

#### Syntax
```tsx
import { CalendarDays } from "lucide-react" // Example icon

import {
  Avatar,
  AvatarFallback,
  AvatarImage,
} from "@/components/ui/avatar" // Example usage
import { Button } from "@/components/ui/button" // Example usage
import {
  HoverCard,
  HoverCardContent,
  HoverCardTrigger,
} from "@/components/ui/hover-card"

export function HoverCardDemo() {
  return (
    <HoverCard>
      <HoverCardTrigger asChild>
        <Button variant="link">@nextjs</Button>
      </HoverCardTrigger>
      <HoverCardContent className="w-80">
        <div className="flex justify-between space-x-4">
          <Avatar>
            <AvatarImage src="https://github.com/vercel.png" />
            <AvatarFallback>VC</AvatarFallback>
          </Avatar>
          <div className="space-y-1">
            <h4 className="text-sm font-semibold">@nextjs</h4>
            <p className="text-sm">
              The React Framework – created and maintained by @vercel.
            </p>
            <div className="flex items-center pt-2">
              <CalendarDays className="mr-2 h-4 w-4 opacity-70" />{" "}
              <span className="text-xs text-muted-foreground">
                Joined December 2021
              </span>
            </div>
          </div>
        </div>
      </HoverCardContent>
    </HoverCard>
  )
}
```

#### Rules
- Wrap the trigger element with `HoverCardTrigger`. Use `asChild` if the trigger is a custom component like `Button`.
- `HoverCardContent` contains the content to be displayed on hover.
- The content appears when the user hovers over the `HoverCardTrigger`.

---

### Input
Displays a form input field or a component that looks like an input field.
`pnpm dlx shadcn@latest add input`
[Input docs](https://ui.shadcn.com/docs/components/input)

#### Variants
There are no variants for this component. Styles like `disabled` are applied via props/attributes.

#### Syntax
```tsx
import { Input } from "@/components/ui/input"
import { Label } from "@/components/ui/label" // Often used with Label
import { Button } from "@/components/ui/button" // Example usage

<div>
    {/* Basic Input */}
    <Input type="email" placeholder="Email" />

    {/* Disabled Input */}
    <Input disabled type="email" placeholder="Email (disabled)" />

    {/* Input with Label */}
    <div className="grid w-full max-w-sm items-center gap-1.5">
      <Label htmlFor="email-labeled">Email</Label>
      <Input type="email" placeholder="Email" id="email-labeled" />
    </div>

    {/* Input with Button */}
    <div className="flex w-full max-w-sm items-center space-x-2">
      <Input type="email" placeholder="Email" />
      <Button type="submit">Subscribe</Button>
    </div>

    {/* Input type file */}
     <div className="grid w-full max-w-sm items-center gap-1.5">
      <Label htmlFor="picture">Picture</Label>
      <Input id="picture" type="file" />
    </div>
</div>
```

#### Rules
- Use standard HTML `input` attributes like `type`, `placeholder`, `disabled`, `id`, etc.
- For file inputs (`type="file"`), styling might differ slightly across browsers but will adopt the general Shadcn input appearance.
- Often used with `Label` for accessibility. Ensure `htmlFor` on `Label` matches `id` on `Input`.

---

### Label
Renders an accessible label associated with controls.
`pnpm dlx shadcn@latest add label`
[Label docs](https://ui.shadcn.com/docs/components/label)

#### Variants
There are no variants for this component.

#### Syntax
```tsx
import { Label } from "@/components/ui/label"
import { Checkbox } from "@/components/ui/checkbox" // Example usage
import { Input } from "@/components/ui/input" // Example usage

<div>
    {/* Label associated with an Input */}
    <div>
        <Label htmlFor="email-addr">Your email address</Label>
        <Input type="email" placeholder="Email" id="email-addr" />
    </div>

    {/* Label associated with a Checkbox */}
    <div className="flex items-center space-x-2">
        <Checkbox id="terms-label" />
        <Label htmlFor="terms-label">Accept terms and conditions</Label>
    </div>
</div>
```

#### Rules
- The `htmlFor` prop is crucial for accessibility. It should match the `id` of the form control (`Input`, `Checkbox`, `RadioGroup`, `Select`, etc.) it labels.
- Clicking the label will focus or activate the associated control.

---

### Menubar
A visually persistent menu common in desktop applications that provides quick access to a consistent set of commands.
`pnpm dlx shadcn@latest add menubar`
[Menubar docs](https://ui.shadcn.com/docs/components/menubar)

#### Variants
There are no variants for this component.

#### Syntax
```tsx
import {
  Menubar,
  MenubarCheckboxItem,
  MenubarContent,
  MenubarItem,
  MenubarMenu,
  MenubarRadioGroup,
  MenubarRadioItem,
  MenubarSeparator,
  MenubarShortcut,
  MenubarSub,
  MenubarSubContent,
  MenubarSubTrigger,
  MenubarTrigger,
} from "@/components/ui/menubar"

export function MenubarDemo() {
  return (
    <Menubar>
      <MenubarMenu>
        <MenubarTrigger>File</MenubarTrigger>
        <MenubarContent>
          <MenubarItem>
            New Tab <MenubarShortcut>⌘T</MenubarShortcut>
          </MenubarItem>
          <MenubarItem>New Window</MenubarItem>
          <MenubarSeparator />
          <MenubarSub>
             <MenubarSubTrigger>Share</MenubarSubTrigger>
             <MenubarSubContent>
                <MenubarItem>Email link</MenubarItem>
                <MenubarItem>Messages</MenubarItem>
             </MenubarSubContent>
          </MenubarSub>
          <MenubarSeparator />
          <MenubarItem>Print</MenubarItem>
        </MenubarContent>
      </MenubarMenu>
      <MenubarMenu>
        <MenubarTrigger>Edit</MenubarTrigger>
        <MenubarContent>
           <MenubarItem>Undo</MenubarItem>
           {/* ... Other edit items ... */}
           <MenubarSeparator />
           <MenubarCheckboxItem checked>Always Show Bookmarks Bar</MenubarCheckboxItem>
           {/* ... Other edit items ... */}
        </MenubarContent>
      </MenubarMenu>
       {/* ... Other Menus (View, Profile etc.) ... */}
    </Menubar>
  )
}
```

#### Rules
- Each top-level menu is defined by a `MenubarMenu` containing a `MenubarTrigger` (the visible part, e.g., "File") and `MenubarContent` (the dropdown).
- `MenubarContent` holds the menu items (`MenubarItem`, `MenubarCheckboxItem`, `MenubarRadioItem` within `MenubarRadioGroup`, etc.), separators (`MenubarSeparator`), and submenus (`MenubarSub`).
- Submenus follow a similar structure with `MenubarSubTrigger` and `MenubarSubContent`.

---

### Navigation Menu
A collection of links for navigating websites. Supports submenus and indicators.
`pnpm dlx shadcn@latest add navigation-menu`
[Navigation Menu docs](https://ui.shadcn.com/docs/components/navigation-menu)

#### Variants
There are no variants for the component itself, but the display and layout are highly customizable via structure and CSS.

#### Syntax
```tsx
"use client" // Required for internal state and link components

import * as React from "react"
import Link from "next/link" // Example usage with Next.js Link
import { cn } from "@/lib/utils"
// import { Icons } from "@/components/icons" // Example for custom icons
import {
  NavigationMenu,
  NavigationMenuContent,
  NavigationMenuItem,
  NavigationMenuLink,
  NavigationMenuList,
  NavigationMenuTrigger,
  navigationMenuTriggerStyle, // Style helper for links acting as triggers
} from "@/components/ui/navigation-menu"

const components: { title: string; href: string; description: string }[] = [
  {
    title: "Alert Dialog",
    href: "/docs/primitives/alert-dialog",
    description: "...",
  },
  // ... other components
]

export function NavigationMenuDemo() {
  return (
    <NavigationMenu>
      <NavigationMenuList>
        <NavigationMenuItem>
          <NavigationMenuTrigger>Getting started</NavigationMenuTrigger>
          <NavigationMenuContent>
            <ul className="grid gap-3 p-4 md:w-[400px] lg:w-[500px] lg:grid-cols-[.75fr_1fr]">
              <li className="row-span-3">
                <NavigationMenuLink asChild>
                  <a
                    className="flex h-full w-full select-none flex-col justify-end rounded-md bg-gradient-to-b from-muted/50 to-muted p-6 no-underline outline-none focus:shadow-md"
                    href="/"
                  >
                    {/* <Icons.logo className="h-6 w-6" /> */}
                    <div className="mb-2 mt-4 text-lg font-medium">
                      shadcn/ui
                    </div>
                    <p className="text-sm leading-tight text-muted-foreground">
                      Beautifully designed components built with Radix UI and Tailwind CSS.
                    </p>
                  </a>
                </NavigationMenuLink>
              </li>
              <ListItem href="/docs" title="Introduction">
                Re-usable components built using Radix UI and Tailwind CSS.
              </ListItem>
              {/* ... more ListItems ... */}
            </ul>
          </NavigationMenuContent>
        </NavigationMenuItem>
        <NavigationMenuItem>
          <NavigationMenuTrigger>Components</NavigationMenuTrigger>
          <NavigationMenuContent>
            <ul className="grid w-[400px] gap-3 p-4 md:w-[500px] md:grid-cols-2 lg:w-[600px] ">
              {components.map((component) => (
                <ListItem
                  key={component.title}
                  title={component.title}
                  href={component.href}
                >
                  {component.description}
                </ListItem>
              ))}
            </ul>
          </NavigationMenuContent>
        </NavigationMenuItem>
        <NavigationMenuItem>
          {/* Example of a simple link */}
          <Link href="/docs" legacyBehavior passHref>
            <NavigationMenuLink className={navigationMenuTriggerStyle()}>
              Documentation
            </NavigationMenuLink>
          </Link>
        </NavigationMenuItem>
      </NavigationMenuList>
    </NavigationMenu>
  )
}

// Helper component often used within NavigationMenuContent
const ListItem = React.forwardRef<
  React.ElementRef<"a">,
  React.ComponentPropsWithoutRef<"a">
>(({ className, title, children, ...props }, ref) => {
  return (
    <li>
      <NavigationMenuLink asChild>
        <a
          ref={ref}
          className={cn(
            "block select-none space-y-1 rounded-md p-3 leading-none no-underline outline-none transition-colors hover:bg-accent hover:text-accent-foreground focus:bg-accent focus:text-accent-foreground",
            className
          )}
          {...props}
        >
          <div className="text-sm font-medium leading-none">{title}</div>
          <p className="line-clamp-2 text-sm leading-snug text-muted-foreground">
            {children}
          </p>
        </a>
      </NavigationMenuLink>
    </li>
  )
})
ListItem.displayName = "ListItem"

```

#### Rules
- Requires `"use client"` for interactivity and often integrates with routing libraries like Next.js `Link`.
- Structure: `NavigationMenu` > `NavigationMenuList` > `NavigationMenuItem`.
- For items with dropdowns: `NavigationMenuItem` > `NavigationMenuTrigger` + `NavigationMenuContent`.
- For simple links: `NavigationMenuItem` > `Link` (or `a`) > `NavigationMenuLink`. Use `navigationMenuTriggerStyle()` helper for consistent styling.
- `NavigationMenuContent` contains the dropdown layout, often using `ul` and custom `ListItem` components for structure and styling.
- `NavigationMenuLink` is used inside `NavigationMenuContent` and for simple top-level links to ensure proper styling and accessibility integration. Use `asChild` when wrapping custom elements like `a` or `Link`.

---

### Popover
Displays rich content in a portal, triggered by a button.
`pnpm dlx shadcn@latest add popover`
[Popover docs](https://ui.shadcn.com/docs/components/popover)

#### Variants
There are no variants for this component.

#### Syntax
```tsx
import { Button } from "@/components/ui/button" // Example trigger
import { Input } from "@/components/ui/input" // Example content
import { Label } from "@/components/ui/label" // Example content
import {
  Popover,
  PopoverContent,
  PopoverTrigger,
} from "@/components/ui/popover"

export function PopoverDemo() {
  return (
    <Popover>
      <PopoverTrigger asChild>
        <Button variant="outline">Open popover</Button>
      </PopoverTrigger>
      <PopoverContent className="w-80">
        <div className="grid gap-4">
          <div className="space-y-2">
            <h4 className="font-medium leading-none">Dimensions</h4>
            <p className="text-sm text-muted-foreground">
              Set the dimensions for the layer.
            </p>
          </div>
          <div className="grid gap-2">
             {/* Example content inside popover */}
            <div className="grid grid-cols-3 items-center gap-4">
              <Label htmlFor="width">Width</Label>
              <Input id="width" defaultValue="100%" className="col-span-2 h-8" />
            </div>
            <div className="grid grid-cols-3 items-center gap-4">
              <Label htmlFor="maxWidth">Max. width</Label>
              <Input id="maxWidth" defaultValue="300px" className="col-span-2 h-8" />
            </div>
            {/* ... more inputs ... */}
          </div>
        </div>
      </PopoverContent>
    </Popover>
  )
}```

#### Rules
- Wrap the trigger element with `PopoverTrigger`. Use `asChild` for custom components like `Button`.
- `PopoverContent` contains the content to be displayed in the popover overlay.
- The popover appears when the `PopoverTrigger` is clicked. It closes on click outside, `Escape` key, or focusing outside.

---

### Progress
Displays an indicator showing the completion progress of a task, typically displayed as a progress bar.
`pnpm dlx shadcn@latest add progress`
[Progress docs](https://ui.shadcn.com/docs/components/progress)

#### Variants
There are no variants for this component. The progress value is controlled via the `value` prop.

#### Syntax
```tsx
import * as React from "react"
import { Progress } from "@/components/ui/progress"

export function ProgressDemo() {
  const [progress, setProgress] = React.useState(13)

  // Example timer to simulate progress change
  React.useEffect(() => {
    const timer = setTimeout(() => setProgress(66), 500)
    return () => clearTimeout(timer)
  }, [])

  return <Progress value={progress} className="w-[60%]" />
}
```

#### Rules
- Requires client-side state (`useState`, `useEffect`) if the progress value changes dynamically. Mark parent component with `"use client"` if needed.
- The `value` prop should be a number between 0 and 100 (or the `max` value if set on the underlying Radix primitive, though not directly exposed in the default shadcn component).
- A `className` can be provided to control width, margins, etc.

---

### Radio Group
A set of checkable buttons—known as radio buttons—where no more than one of the buttons can be checked at a time.
`pnpm dlx shadcn@latest add radio-group label`
[Radio Group docs](https://ui.shadcn.com/docs/components/radio-group)

#### Variants
There are no variants for this component.

#### Syntax
```tsx
"use client" // If used interactively with state

import { Label } from "@/components/ui/label"
import { RadioGroup, RadioGroupItem } from "@/components/ui/radio-group"
import * as React from "react" // If using state

export function RadioGroupDemo() {
    // Example state management
    const [selectedValue, setSelectedValue] = React.useState("default")

  return (
    <RadioGroup
        defaultValue="comfortable" // Or use value={selectedValue} for controlled
        // onValueChange={setSelectedValue} // For controlled component
        className="gap-4" // Example layout styling
    >
      <div className="flex items-center space-x-2">
        <RadioGroupItem value="default" id="r1" />
        <Label htmlFor="r1">Default</Label>
      </div>
      <div className="flex items-center space-x-2">
        <RadioGroupItem value="comfortable" id="r2" />
        <Label htmlFor="r2">Comfortable</Label>
      </div>
      <div className="flex items-center space-x-2">
        <RadioGroupItem value="compact" id="r3" />
        <Label htmlFor="r3">Compact</Label>
      </div>
    </RadioGroup>
  )
}
```

#### Rules
- Use `RadioGroup` to wrap multiple `RadioGroupItem` elements.
- Each `RadioGroupItem` needs a unique `id` and a `value`.
- Use `Label` components associated with each `RadioGroupItem` via `htmlFor` pointing to the item's `id`.
- Can be controlled (using `value` and `onValueChange` props with state) or uncontrolled (using `defaultValue`). Requires `"use client"` if controlled.

---

### Resizable
Accessible implementation of a panel group and interactive resizing panel component.
`pnpm dlx shadcn@latest add resizable`
[Resizable docs](https://ui.shadcn.com/docs/components/resizable)

#### Variants
There are no variants, but behavior is controlled by props like `direction`.

#### Syntax
```tsx
import {
  ResizableHandle,
  ResizablePanel,
  ResizablePanelGroup,
} from "@/components/ui/resizable"

export function ResizableDemo() {
  return (
    <ResizablePanelGroup
      direction="horizontal" // or "vertical"
      className="max-w-md rounded-lg border" // Example styling
    >
      <ResizablePanel defaultSize={50}>
        <div className="flex h-[200px] items-center justify-center p-6">
          <span className="font-semibold">One</span>
        </div>
      </ResizablePanel>
      <ResizableHandle withHandle /> {/* Adds a visual handle */}
      <ResizablePanel defaultSize={50}>
        <ResizablePanelGroup direction="vertical">
          <ResizablePanel defaultSize={25}>
            <div className="flex h-full items-center justify-center p-6">
              <span className="font-semibold">Two</span>
            </div>
          </ResizablePanel>
          <ResizableHandle withHandle />
          <ResizablePanel defaultSize={75}>
            <div className="flex h-full items-center justify-center p-6">
              <span className="font-semibold">Three</span>
            </div>
          </ResizablePanel>
        </ResizablePanelGroup>
      </ResizablePanel>
    </ResizablePanelGroup>
  )
}
```

#### Rules
- Structure: `ResizablePanelGroup` wraps `ResizablePanel` and `ResizableHandle` components.
- `direction` prop on `ResizablePanelGroup` determines if panels resize horizontally or vertically.
- `ResizableHandle` is placed between `ResizablePanel`s to allow dragging. Add `withHandle` prop for a visual indicator.
- `ResizablePanel`s contain the actual content for each panel. `defaultSize` prop (percentage) controls initial size distribution.
- `ResizablePanelGroup`s can be nested for complex layouts.

---

### Scroll Area
Augments native scroll functionality for custom, cross-browser styling.
`pnpm dlx shadcn@latest add scroll-area`
[Scroll Area docs](https://ui.shadcn.com/docs/components/scroll-area)

#### Variants
There are no variants for this component. Scrollbar visibility and orientation are handled internally or via props/CSS.

#### Syntax
```tsx
import { ScrollArea, ScrollBar } from "@/components/ui/scroll-area"
import { Separator } from "@/components/ui/separator" // Example usage

interface Artwork {
  artist: string
  art: string
}

const works: Artwork[] = [
  { artist: "Artist 1", art: "Art 1 Title" },
  // ... more artworks
]

export function ScrollAreaDemo() {
  return (
    <ScrollArea className="h-72 w-48 rounded-md border"> {/* Vertical scroll example */}
      <div className="p-4">
        <h4 className="mb-4 text-sm font-medium leading-none">Tags</h4>
        {works.map((artwork) => (
          <React.Fragment key={artwork.artist}>
            <div className="text-sm">
              {artwork.artist}
            </div>
            <Separator className="my-2" />
          </React.Fragment>
        ))}
      </div>
    </ScrollArea>

    {/* Horizontal scroll example */}
    {/* <ScrollArea className="w-96 whitespace-nowrap rounded-md border">
      <div className="flex w-max space-x-4 p-4">
        {works.map((artwork) => (
          <figure key={artwork.artist} className="shrink-0">
            <div className="overflow-hidden rounded-md">
              <img ... /> // Add image component here
            </div>
            <figcaption>...</figcaption>
          </figure>
        ))}
      </div>
      <ScrollBar orientation="horizontal" />
    </ScrollArea> */}
  )
}

```

#### Rules
- Wrap the content that needs scrolling within `ScrollArea`.
- Define the size (height/width) of the `ScrollArea` using CSS classes (e.g., `h-72 w-48`). The content inside can then exceed these dimensions.
- By default, vertical scrollbars appear automatically when needed.
- To enable horizontal scrolling, ensure the inner content doesn't wrap (`whitespace-nowrap` on parent, fixed widths on children) and explicitly add `<ScrollBar orientation="horizontal" />`.

---

### Select
Displays a list of options for the user to pick from—triggered by a button.
`pnpm dlx shadcn@latest add select`
[Select docs](https://ui.shadcn.com/docs/components/select)

#### Variants
There are no variants for this component.

#### Syntax
```tsx
import {
  Select,
  SelectContent,
  SelectGroup,
  SelectItem,
  SelectLabel,
  SelectSeparator,
  SelectTrigger,
  SelectValue,
} from "@/components/ui/select"

export function SelectDemo() {
  return (
    <Select>
      <SelectTrigger className="w-[180px]">
        <SelectValue placeholder="Select a fruit" />
      </SelectTrigger>
      <SelectContent>
        <SelectGroup>
          <SelectLabel>Fruits</SelectLabel>
          <SelectItem value="apple">Apple</SelectItem>
          <SelectItem value="banana">Banana</SelectItem>
          <SelectItem value="blueberry">Blueberry</SelectItem>
          <SelectItem value="grapes">Grapes</SelectItem>
          <SelectItem value="pineapple">Pineapple</SelectItem>
        </SelectGroup>
         <SelectSeparator /> {/* Optional separator */}
         <SelectGroup>
            <SelectLabel>Vegetables</SelectLabel>
            <SelectItem value="carrot">Carrot</SelectItem>
            <SelectItem value="celery">Celery</SelectItem>
         </SelectGroup>
      </SelectContent>
    </Select>
  )
}
```

#### Rules
- `SelectTrigger` is the clickable element that opens the dropdown and displays the selected value (or placeholder).
- `SelectValue` displays the selected value within the trigger. Use the `placeholder` prop for initial text.
- `SelectContent` contains the list of options.
- `SelectItem` represents each option. The `value` prop is the actual value submitted or used in state; the content between the tags is what's displayed.
- `SelectGroup` can wrap sets of items, often preceded by a `SelectLabel`.
- `SelectSeparator` can visually divide groups of items.
- State management (getting the selected value) is typically done via the `onValueChange` prop on the root `Select` component or by using it within a form library like React Hook Form.

---

### Separator
Visually or semantically separates content.
`pnpm dlx shadcn@latest add separator`
[Separator docs](https://ui.shadcn.com/docs/components/separator)

#### Variants
There are no variants, but orientation is controlled via the `orientation` prop.

#### Syntax
```tsx
import { Separator } from "@/components/ui/separator"

export function SeparatorDemo() {
  return (
    <div>
      <div className="space-y-1">
        <h4 className="text-sm font-medium leading-none">Radix Primitives</h4>
        <p className="text-sm text-muted-foreground">
          An open-source UI component library.
        </p>
      </div>
      <Separator className="my-4" /> {/* Default horizontal */}
      <div className="flex h-5 items-center space-x-4 text-sm">
        <div>Blog</div>
        <Separator orientation="vertical" /> {/* Vertical */}
        <div>Docs</div>
        <Separator orientation="vertical" />
        <div>Source</div>
      </div>
    </div>
  )
}
```

#### Rules
- By default, renders a horizontal line.
- Use `orientation="vertical"` for a vertical line. Ensure the parent container uses flexbox or similar layout to give the vertical separator height.
- Use utility classes (like `my-4`, `mx-2`) for spacing around the separator.

---

### Sheet
Extends the Dialog component to display content that complements the main content of the screen. Appears as a side panel.
`pnpm dlx shadcn@latest add sheet`
[Sheet docs](https://ui.shadcn.com/docs/components/sheet)

#### Variants
**Sheet**
- **side**: `"top"`, `"bottom"`, `"left"`, `"right"` (Determines which edge the sheet slides in from)

#### Syntax
```tsx
import { Button } from "@/components/ui/button" // Example trigger
import { Input } from "@/components/ui/input" // Example content
import { Label } from "@/components/ui/label" // Example content
import {
  Sheet,
  SheetClose,
  SheetContent,
  SheetDescription,
  SheetFooter,
  SheetHeader,
  SheetTitle,
  SheetTrigger,
} from "@/components/ui/sheet"

export function SheetDemo() {
  const SHEET_SIDES = ["top", "right", "bottom", "left"] as const

  return (
    <div className="grid grid-cols-2 gap-2">
        {/* Example creating a trigger for each side */}
      {SHEET_SIDES.map((side) => (
        <Sheet key={side}>
          <SheetTrigger asChild>
            <Button variant="outline">{side}</Button>
          </SheetTrigger>
          <SheetContent side={side}> {/* Control side here */}
            <SheetHeader>
              <SheetTitle>Edit profile</SheetTitle>
              <SheetDescription>
                Make changes to your profile here. Click save when you're done.
              </SheetDescription>
            </SheetHeader>
            <div className="grid gap-4 py-4">
              {/* Example content */}
              <div className="grid grid-cols-4 items-center gap-4">
                <Label htmlFor="name" className="text-right">Name</Label>
                <Input id="name" value="Pedro Duarte" className="col-span-3" />
              </div>
              {/* ... more inputs ... */}
            </div>
            <SheetFooter>
              <SheetClose asChild>
                <Button type="submit">Save changes</Button>
              </SheetClose>
            </SheetFooter>
          </SheetContent>
        </Sheet>
      ))}
    </div>
  )
}
```

#### Rules
- Structure is very similar to `Dialog`: `SheetTrigger`, `SheetContent`, `SheetHeader`, `SheetTitle`, `SheetDescription`, `SheetFooter`, `SheetClose`.
- Use the `side` prop on `SheetContent` to control the animation origin (`top`, `bottom`, `left`, `right`). Default is usually `right`.
- Use `SheetTrigger` with `asChild` for custom trigger components.
- `SheetClose` can be used to wrap elements (like buttons) that should close the sheet on click. Closing also occurs on `Escape` or clicking outside the sheet.

---

### Skeleton
Use to show a placeholder preview of your content before the data gets loaded to reduce load-time frustration.
`pnpm dlx shadcn@latest add skeleton`
[Skeleton docs](https://ui.shadcn.com/docs/components/skeleton)

#### Variants
There are no variants for this component. Shape and size are controlled via CSS classes.

#### Syntax
```tsx
import { Skeleton } from "@/components/ui/skeleton"

export function SkeletonDemo() {
  return (
    <div className="flex items-center space-x-4">
      <Skeleton className="h-12 w-12 rounded-full" /> {/* Matches Avatar */}
      <div className="space-y-2">
        <Skeleton className="h-4 w-[250px]" /> {/* Matches a line of text */}
        <Skeleton className="h-4 w-[200px]" /> {/* Matches another line */}
      </div>
    </div>
  )
}
```

#### Rules
- Apply utility classes (height `h-`, width `w-`, border-radius `rounded-`, etc.) to the `Skeleton` component to match the dimensions and shape of the content it's replacing.
- Often used in lists or cards where data is being fetched asynchronously.

---

### Slider
An input where the user selects a value from within a given range.
`pnpm dlx shadcn@latest add slider`
[Slider docs](https://ui.shadcn.com/docs/components/slider)

#### Variants
There are no variants for this component. Behavior like range, step, and orientation are controlled by props.

#### Syntax
```tsx
"use client" // Required for state management

import { Slider } from "@/components/ui/slider"
import { cn } from "@/lib/utils"
import * as React from "react" // For state

type SliderProps = React.ComponentProps<typeof Slider>

export function SliderDemo({ className, ...props }: SliderProps) {
    // Example state for controlled slider value
    const [value, setValue] = React.useState([50]) // Default value in an array

  return (
    <div>
        {/* Controlled Slider */}
        <Slider
            defaultValue={[50]} // Or value={value} for controlled
            max={100}
            step={1}
            className={cn("w-[60%]", className)}
            onValueChange={(newValue) => setValue(newValue)} // Handle value change
            {...props}
        />
        <div className="mt-2">Current Value: {value[0]}</div>

        {/* Uncontrolled Slider with default */}
         {/* <Slider
            defaultValue={[33]}
            max={100}
            step={1}
            className={cn("w-[60%]", className)}
            {...props}
        /> */}
    </div>

  )
}
```

#### Rules
- The value is typically represented as an array (e.g., `[50]`) even for single-thumb sliders, to accommodate range sliders (multiple thumbs).
- Props:
    - `defaultValue`: For uncontrolled components.
    - `value`: For controlled components (requires state and `onValueChange`).
    - `onValueChange`: Callback function that receives the new value array when the slider is moved.
    - `max`: Maximum value (default 100).
    - `min`: Minimum value (default 0).
    - `step`: Increment value (default 1).
    - `minStepsBetweenThumbs`: For range sliders, the minimum distance between thumbs.
    - `orientation`: `"horizontal"` (default) or `"vertical"`.
    - `inverted`: Flips the direction of the slider.
    - `disabled`: Disables interaction.
- Requires `"use client"` if used as a controlled component.

---

### Sonner (Toast)
An opinionated toast component for React. Installs as `sonner` but is often used via a `toast` function.
`pnpm dlx shadcn@latest add sonner`
[Sonner docs](https://ui.shadcn.com/docs/components/sonner)

#### Variants
**Toast Function (`toast()`)**
- **Types**: `toast('Event has been created')` (default), `toast.success('Event has been created')`, `toast.info('Beep boop...')`, `toast.warning('Event has warnings...')`, `toast.error('Event has failed to create')`, `toast.message('Custom Title', { description: '...' })`, `toast.promise(promise, { loading: '...', success: '...', error: '...' })`
- **Position**: Controlled globally via the `<Toaster />` component (`position` prop: `"top-left"`, `"top-center"`, `"top-right"`, `"bottom-left"`, `"bottom-center"`, `"bottom-right"`).

#### Syntax
```tsx
// 1. Add Toaster to your root layout (e.g., layout.tsx)
import { Toaster } from "@/components/ui/sonner"

function RootLayout({ children }: { children: React.ReactNode }) {
  return (
    <html>
      <body>
        {children}
        <Toaster position="top-center" richColors /> {/* Example position and style */}
      </body>
    </html>
  )
}


// 2. Use the toast function in your components
"use client" // Required to call the toast function

import { Button } from "@/components/ui/button"
import { toast } from "sonner" // Import directly from sonner

export function SonnerDemo() {
  return (
    <div className="grid grid-cols-4 gap-4">
        <Button
            variant="outline"
            onClick={() => toast("Event has been created.")}
            >
            Show Toast (Default)
        </Button>

        <Button
            variant="outline"
            onClick={() => toast.success("Event successful!")}
            >
            Show Toast (Success)
        </Button>

         <Button
            variant="outline"
            onClick={() => toast.error("Something went wrong!")}
            >
            Show Toast (Error)
        </Button>

         <Button
            variant="outline"
            onClick={() => toast.message('Event Added', { description: 'Monday, December 6th at 10:00 AM' })}
            >
            Show Toast (Message)
        </Button>

         <Button
            variant="outline"
            onClick={() => {
                const promise = () => new Promise((resolve) => setTimeout(() => resolve({ name: 'Sonner' }), 2000));
                toast.promise(promise, {
                    loading: 'Loading...',
                    success: (data) => `Toast for ${data.name} has been added!`,
                    error: 'Error',
                });
            }}
            >
            Show Toast (Promise)
        </Button>

         <Button
            variant="outline"
            onClick={() => toast("Event has been created.", {
                action: {
                    label: "Undo",
                    onClick: () => console.log("Undo"),
                },
            })}
            >
            Show Toast (With Action)
        </Button>
    </div>
  )
}
```

#### Rules
- Install the `sonner` library. Shadcn's `add sonner` command adds a pre-styled `Toaster` component (`@/components/ui/sonner`).
- Place the `<Toaster />` component once in your application's root layout or main page component. Customize its props (`position`, `richColors`, `theme`, `closeButton`, etc.) as needed.
- Import the `toast` function directly from the `sonner` library (`import { toast } from "sonner"`).
- Call the `toast()` function (or its variants like `toast.success`, `toast.error`, `toast.promise`) from client components (`"use client"`) where you want to trigger a notification (e.g., in button click handlers, after form submissions).
- The `toast` function can accept an options object for customization (e.g., adding actions, descriptions, durations).

---

### Switch
A control that allows the user to toggle between checked and unchecked states.
`pnpm dlx shadcn@latest add switch label`
[Switch docs](https://ui.shadcn.com/docs/components/switch)

#### Variants
There are no variants for this component.

#### Syntax
```tsx
"use client" // If used interactively with state

import { Label } from "@/components/ui/label"
import { Switch } from "@/components/ui/switch"
import * as React from "react" // If using state

export function SwitchDemo() {
    // Example state management
    const [checked, setChecked] = React.useState(false)

  return (
    <div className="flex items-center space-x-2">
      <Switch
        id="airplane-mode"
        checked={checked} // For controlled component
        onCheckedChange={setChecked} // For controlled component
        // defaultChecked={true} // For uncontrolled component
       />
      <Label htmlFor="airplane-mode">Airplane Mode</Label>
    </div>
  )
}
```

#### Rules
- Often used with a `Label`. Ensure the `htmlFor` prop on `Label` matches the `id` prop on `Switch`.
- Can be controlled (using `checked` and `onCheckedChange` props with state) or uncontrolled (using `defaultChecked`). Requires `"use client"` if controlled.
- The `onCheckedChange` callback receives the new boolean checked state.

---

### Table
Displays data in rows and columns.
`pnpm dlx shadcn@latest add table`
[Table docs](https://ui.shadcn.com/docs/components/table)

#### Variants
There are no variants for this component. Styling is applied via utility classes and nested structure.

#### Syntax
```tsx
import {
  Table,
  TableBody,
  TableCaption,
  TableCell,
  TableFooter,
  TableHead,
  TableHeader,
  TableRow,
} from "@/components/ui/table"

const invoices = [
  { invoice: "INV001", paymentStatus: "Paid", totalAmount: "$250.00", paymentMethod: "Credit Card" },
  // ... more invoices
]

export function TableDemo() {
  return (
    <Table>
      <TableCaption>A list of your recent invoices.</TableCaption>
      <TableHeader>
        <TableRow>
          <TableHead className="w-[100px]">Invoice</TableHead>
          <TableHead>Status</TableHead>
          <TableHead>Method</TableHead>
          <TableHead className="text-right">Amount</TableHead>
        </TableRow>
      </TableHeader>
      <TableBody>
        {invoices.map((invoice) => (
          <TableRow key={invoice.invoice}>
            <TableCell className="font-medium">{invoice.invoice}</TableCell>
            <TableCell>{invoice.paymentStatus}</TableCell>
            <TableCell>{invoice.paymentMethod}</TableCell>
            <TableCell className="text-right">{invoice.totalAmount}</TableCell>
          </TableRow>
        ))}
      </TableBody>
      <TableFooter>
        <TableRow>
          <TableCell colSpan={3}>Total</TableCell>
          <TableCell className="text-right">$2,500.00</TableCell>
        </TableRow>
      </TableFooter>
    </Table>
  )
}
```

#### Rules
- Uses standard HTML table structure (`table`, `thead`, `tbody`, `tfoot`, `tr`, `th`, `td`) mapped to corresponding components (`Table`, `TableHeader`, `TableBody`, `TableFooter`, `TableRow`, `TableHead`, `TableCell`).
- `TableCaption` provides an accessible description for the table.
- Use utility classes for alignment (`text-right`), width (`w-[100px]`), font weight (`font-medium`), etc., directly on `TableHead` and `TableCell` as needed.
- For complex features like sorting, filtering, and pagination, consider using the Data Table pattern which integrates `@tanstack/react-table`.

---

### Tabs
A set of layered sections of content—known as tab panels—that are displayed one at a time.
`pnpm dlx shadcn@latest add tabs`
[Tabs docs](https://ui.shadcn.com/docs/components/tabs)

#### Variants
There are no variants for this component.

#### Syntax
```tsx
import { Button } from "@/components/ui/button" // Example content
import { Card, CardContent, CardDescription, CardFooter, CardHeader, CardTitle } from "@/components/ui/card" // Example content
import { Input } from "@/components/ui/input" // Example content
import { Label } from "@/components/ui/label" // Example content
import { Tabs, TabsContent, TabsList, TabsTrigger } from "@/components/ui/tabs"

export function TabsDemo() {
  return (
    <Tabs defaultValue="account" className="w-[400px]">
      <TabsList className="grid w-full grid-cols-2">
        <TabsTrigger value="account">Account</TabsTrigger>
        <TabsTrigger value="password">Password</TabsTrigger>
      </TabsList>
      <TabsContent value="account">
        <Card>
          <CardHeader>
            <CardTitle>Account</CardTitle>
            <CardDescription>
              Make changes to your account here. Click save when you're done.
            </CardDescription>
          </CardHeader>
          <CardContent className="space-y-2">
            <div className="space-y-1">
              <Label htmlFor="name">Name</Label>
              <Input id="name" defaultValue="Pedro Duarte" />
            </div>
            {/* ... more inputs ... */}
          </CardContent>
          <CardFooter>
            <Button>Save changes</Button>
          </CardFooter>
        </Card>
      </TabsContent>
      <TabsContent value="password">
        <Card>
          <CardHeader>
            <CardTitle>Password</CardTitle>
            <CardDescription>
              Change your password here. After saving, you'll be logged out.
            </CardDescription>
          </CardHeader>
          <CardContent className="space-y-2">
             <div className="space-y-1">
                <Label htmlFor="current">Current password</Label>
                <Input id="current" type="password" />
            </div>
             {/* ... more inputs ... */}
          </CardContent>
          <CardFooter>
            <Button>Save password</Button>
          </CardFooter>
        </Card>
      </TabsContent>
    </Tabs>
  )
}
```

#### Rules
- `Tabs` is the root component, use `defaultValue` to set the initially active tab.
- `TabsList` wraps the `TabsTrigger` components.
- `TabsTrigger` is a clickable button for switching tabs. Its `value` prop must match the `value` of the corresponding `TabsContent`.
- `TabsContent` wraps the content for each tab. Its `value` prop links it to a `TabsTrigger`. Only the content for the active tab is visible.
- Use layout utilities (like `grid` in the example) on `TabsList` if you want the triggers to fill the width.

---

### Textarea
Displays a multi-line text input field.
`pnpm dlx shadcn@latest add textarea`
[Textarea docs](https://ui.shadcn.com/docs/components/textarea)

#### Variants
There are no variants for this component. Styling like `disabled` is applied via props/attributes.

#### Syntax
```tsx
import { Textarea } from "@/components/ui/textarea"
import { Label } from "@/components/ui/label" // Example usage
import { Button } from "@/components/ui/button" // Example usage

<div>
    {/* Basic Textarea */}
    <Textarea placeholder="Type your message here." />

    {/* Disabled Textarea */}
    <Textarea placeholder="Type your message here (disabled)." disabled />

    {/* Textarea with Label */}
    <div className="grid w-full gap-1.5">
      <Label htmlFor="message-labeled">Your message</Label>
      <Textarea placeholder="Type your message here." id="message-labeled" />
    </div>

    {/* Textarea with Button */}
    <div className="grid w-full gap-2">
      <Textarea placeholder="Type your message here." />
      <Button>Send message</Button>
    </div>

     {/* Textarea with Text helper */}
      <div className="grid w-full gap-1.5">
        <Label htmlFor="message-helper">Your Message</Label>
        <Textarea placeholder="Type your message here." id="message-helper" />
        <p className="text-sm text-muted-foreground">
          Your message will be copied to the support team.
        </p>
      </div>
</div>
```

#### Rules
- Use standard HTML `textarea` attributes like `placeholder`, `disabled`, `id`, `rows`, etc.
- Often used with `Label` for accessibility. Ensure `htmlFor` on `Label` matches `id` on `Textarea`.
- Height adjusts automatically based on content by default, but can be controlled with CSS or the `rows` attribute if needed.

---

### Toast (Deprecated - use Sonner)
Displays a succinct message that informs users about a process happening in the app. (Note: Sonner is generally preferred now).
`pnpm dlx shadcn@latest add toast button`
[Toast docs](https://ui.shadcn.com/docs/components/toast)

#### Variants
**Toast**
- **variant**: `"default"`, `"destructive"`

#### Syntax
```tsx
// 1. Add Toaster to your app (e.g., layout.tsx or page.tsx)
import { Toaster } from "@/components/ui/toaster"

function AppLayout({ children }) {
  return (
    <div>
      {children}
      <Toaster />
    </div>
  )
}

// 2. Use the `useToast` hook and `toast` function
"use client" // Required for hook and interaction

import { Button } from "@/components/ui/button"
import { ToastAction } from "@/components/ui/toast" // For actions
import { useToast } from "@/components/ui/use-toast" // Import the hook

export function ToastDemo() {
  const { toast } = useToast() // Get the toast function from the hook

  return (
    <div className="grid grid-cols-4 gap-4">
        <Button
        variant="outline"
        onClick={() => {
            toast({
            title: "Scheduled: Catch up",
            description: "Friday, February 10, 2023 at 5:57 PM",
            })
        }}
        >
        Show Toast (Default)
        </Button>

        <Button
        variant="outline"
        onClick={() => {
            toast({
            variant: "destructive",
            title: "Uh oh! Something went wrong.",
            description: "There was a problem with your request.",
            action: <ToastAction altText="Try again">Try again</ToastAction>,
            })
        }}
        >
        Show Toast (Destructive)
        </Button>

        <Button
        variant="outline"
        onClick={() => {
            toast({
            title: "Simple Toast",
            })
        }}
        >
        Show Toast (Simple)
        </Button>
    </div>
  )
}

```

#### Rules
- Add the `<Toaster />` component (from `@/components/ui/toaster`) once in your application, usually in the root layout.
- Import and use the `useToast` hook (from `@/components/ui/use-toast`) within client components (`"use client"`) where you want to trigger toasts.
- Call the `toast()` function returned by the hook, passing an object with `title`, `description`, `variant`, and `action` (using `ToastAction` component) as needed.
- **Note:** Shadcn UI documentation might favor the newer `Sonner` component for toasts. Check the latest recommendations.

---

### Toggle
A two-state button that can be either on or off.
`pnpm dlx shadcn@latest add toggle`
[Toggle docs](https://ui.shadcn.com/docs/components/toggle)

#### Variants
**Toggle**
- **variant**: `"default"`, `"outline"`
- **size**: `"default"`, `"sm"`, `"lg"`

#### Syntax
```tsx
import { FontBoldIcon, FontItalicIcon, UnderlineIcon } from "@radix-ui/react-icons" // Example icons
import { Toggle } from "@/components/ui/toggle"

export function ToggleDemo() {
  return (
    <div>
        {/* Basic Toggle */}
        <Toggle aria-label="Toggle italic">
            <FontItalicIcon className="h-4 w-4" />
        </Toggle>

        {/* Toggle with Text */}
        <Toggle aria-label="Toggle placeholder">
           <span>Text</span>
        </Toggle>

        {/* Outline Variant */}
        <Toggle variant="outline" aria-label="Toggle bold">
            <FontBoldIcon className="h-4 w-4" />
        </Toggle>

        {/* Different Sizes */}
        <Toggle size="sm" aria-label="Toggle underline small">
            <UnderlineIcon className="h-4 w-4" />
        </Toggle>
         <Toggle size="lg" aria-label="Toggle underline large">
            <UnderlineIcon className="h-4 w-4" />
        </Toggle>

        {/* Disabled Toggle */}
        <Toggle aria-label="Toggle italic disabled" disabled>
            <FontItalicIcon className="h-4 w-4" />
        </Toggle>
    </div>
  )
}
```

#### Rules
- Use the `variant` prop for `"default"` or `"outline"` style.
- Use the `size` prop for `"sm"`, `"default"`, or `"lg"` sizing.
- Include an `aria-label` for accessibility, especially when the toggle only contains an icon.
- The pressed state can be controlled using the `pressed` and `onPressedChange` props (requires `"use client"` and state management) or uncontrolled using `defaultPressed`.

---

### Toggle Group
A set of two-state buttons that can be toggled on or off. Can be configured to allow single or multiple selected items.
`pnpm dlx shadcn@latest add toggle-group toggle`
[Toggle Group docs](https://ui.shadcn.com/docs/components/toggle-group)

#### Variants
**ToggleGroup** (Applies to child `ToggleGroupItem`s)
- **variant**: `"default"`, `"outline"`
- **size**: `"default"`, `"sm"`, `"lg"`

#### Syntax
```tsx
import { FontBoldIcon, FontItalicIcon, UnderlineIcon } from "@radix-ui/react-icons" // Example icons
import { ToggleGroup, ToggleGroupItem } from "@/components/ui/toggle-group"

export function ToggleGroupDemo() {
  return (
    <div>
        {/* Multiple Selection (Default) */}
        <ToggleGroup type="multiple" variant="outline">
            <ToggleGroupItem value="bold" aria-label="Toggle bold">
                <FontBoldIcon className="h-4 w-4" />
            </ToggleGroupItem>
            <ToggleGroupItem value="italic" aria-label="Toggle italic">
                <FontItalicIcon className="h-4 w-4" />
            </ToggleGroupItem>
            <ToggleGroupItem value="underline" aria-label="Toggle underline">
                <UnderlineIcon className="h-4 w-4" />
            </ToggleGroupItem>
        </ToggleGroup>

         {/* Single Selection */}
         <ToggleGroup type="single" size="lg" className="mt-4">
             <ToggleGroupItem value="left" aria-label="Left aligned"> Left </ToggleGroupItem>
             <ToggleGroupItem value="center" aria-label="Center aligned"> Center </ToggleGroupItem>
             <ToggleGroupItem value="right" aria-label="Right aligned"> Right </ToggleGroupItem>
         </ToggleGroup>

         {/* Disabled Group */}
         <ToggleGroup type="single" variant="outline" disabled className="mt-4">
             <ToggleGroupItem value="a">A</ToggleGroupItem>
             <ToggleGroupItem value="b">B</ToggleGroupItem>
             <ToggleGroupItem value="c">C</ToggleGroupItem>
         </ToggleGroup>
    </div>
  )
}
```

#### Rules
- Wrap `ToggleGroupItem` elements within a `ToggleGroup`.
- Use `type="single"` to allow only one item to be selected at a time (like radio buttons).
- Use `type="multiple"` (default) to allow multiple items to be selected concurrently (like checkboxes).
- Set `variant` and `size` on the `ToggleGroup` component; these styles propagate to the `ToggleGroupItem` children.
- Each `ToggleGroupItem` requires a unique `value` prop.
- State can be controlled (`value`, `onValueChange`) or uncontrolled (`defaultValue`). `onValueChange` receives the new value (string for `single`, string[] for `multiple`). Requires `"use client"` if controlled.

---

### Tooltip
A popup that displays information related to an element when the element receives keyboard focus or the mouse hovers over it.
`pnpm dlx shadcn@latest add tooltip`
[Tooltip docs](https://ui.shadcn.com/docs/components/tooltip)

#### Variants
There are no variants for this component.

#### Syntax
```tsx
import { Button } from "@/components/ui/button" // Example trigger
import {
  Tooltip,
  TooltipContent,
  TooltipProvider, // Required wrapper
  TooltipTrigger,
} from "@/components/ui/tooltip"

export function TooltipDemo() {
  return (
    // TooltipProvider is necessary, usually placed higher up the tree (e.g., layout)
    <TooltipProvider>
      <Tooltip>
        <TooltipTrigger asChild>
          <Button variant="outline">Hover me</Button>
        </TooltipTrigger>
        <TooltipContent>
          <p>Add to library</p>
        </TooltipContent>
      </Tooltip>
    </TooltipProvider>
  )
}
```

#### Rules
- Wrap the part of your application that uses tooltips with `<TooltipProvider>`. This is often done once near the root of your app.
- For each tooltip instance:
    - Use `<Tooltip>`.
    - Wrap the trigger element with `<TooltipTrigger>`. Use `asChild` for custom components like `Button`.
    - Define the tooltip's content within `<TooltipContent>`.
- The tooltip appears on hover or focus of the `TooltipTrigger`.

```