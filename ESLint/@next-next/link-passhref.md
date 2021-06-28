Pattern: Missing use of `passHref` for `Link`

Issue: -

## Description

`passHref` was not used for a `Link` component that wraps a custom component. This is needed in order to pass the `href` to the child `<a>` tag.

### Possible Ways to Fix It

If you're using a custom component that wraps an `<a>` tag, make sure to add `passHref`:

```jsx
import Link from 'next/link'
import styled from 'styled-components'

const StyledLink = styled.a`
  color: red;
`

function NavLink({ href, name }) {
  return (
    <Link href={href} passHref>
      <StyledLink>{name}</StyledLink>
    </Link>
  )
}

export default NavLink
```

## Further Reading

* [next.js - Link passHref](https://nextjs.org/docs/messages/link-passhref)