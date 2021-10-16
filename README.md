# Snippets

## Componentjs
(No typescript) React component with 'prop-types' validation, dynamic classes with JSS, children elements props factorised inside file as an only object containing all of them. To use with same level refactorization of styles and handlers. Code style to work with https://github.com/standard/eslint-config-standard
Output:

```react
import React, { useState } from 'react'
import { createUseStyles } from 'react-jss'
import { handleOnClick } from './ComponentHandlers.js'
import defaultStyle from './ComponentStyles.js'

const Component = (props) => {
  const styles = { ...defaultStyle, ...props.style }
  const useStyles = createUseStyles(styles)
  const cl = useStyles()
  const childrenElementProps = {
    onClick: () => props.onClick()
  }

  return (
    <div className={cl.back}>
      
    </div>
  )
}

Component.propTypes = {
  onClick: PropTypes.func,
  style: PropTypes.object
}

export default Component

```
