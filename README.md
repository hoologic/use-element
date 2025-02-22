# @hoologic/use-element

React hook providing a typed element DOM reference via a ref callback.

## Usage

import { useElement } from '@hoologic/use-element'
import { useEffect } from 'react'

const Component = () => {
  const [element, refCallback] = useElement<HTMLDivElement>()

  useEffect(() => {
    if (!element) return

    const { height, width } = element.getBoundingClientRect()

    console.log(height, width)
  }, [element])

  return <div ref={refCallback}>Content</div>
}
