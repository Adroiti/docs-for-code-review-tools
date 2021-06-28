Pattern: Use of `<img>`

Issue: -

## Description

An HTML `<img>` element was used to display an image. For better performance and automatic image optimization, use Next.js' built-in image component instead.

### Possible Ways to Fix It

Import and use the `<Image />` component:

```jsx
import Image from 'next/image'

function Home() {
  return (
    <>
      <Image
        src="https://example.com/test"
        alt="Landscape picture"
        width={500}
        height={500}
      />
    </>
  )
}

export default Home
```

## Further Reading

* [next.js - No Img Element](https://nextjs.org/docs/messages/no-img-element)