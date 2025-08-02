# PHP Style Guide

## Structure Rules
- Use 4 spaces for indentation
- Follow PER-CS (https://www.php-fig.org/per/coding-style/)
- Follow Symfony Coding Standards (https://symfony.com/doc/current/contributing/code/standards.html)
- Always declare strict types
- Follow the rules listed in the default .php-cs-fixer.dist.php file described below

## Default .php-cs-fixer.dist.php

Use this file without modification for projects that do not already have a `.php-cs-fixer.dist.php` or `.php-cs-fixer.php` set up. Install this file as `.php-cs-fixer.dist.php`.

```php
<?php

declare(strict_types=1);

use PhpCsFixer\Config;
use PhpCsFixer\Finder;
use PhpCsFixer\Fixer\Internal\ConfigurableFixerTemplateFixer;
use PhpCsFixer\Runner\Parallel\ParallelConfigFactory;

return (new Config())
    ->setParallelConfig(ParallelConfigFactory::detect()) // @TODO 4.0 no need to call this manually
    ->setRiskyAllowed(true)
    ->setUsingCache(true)
        ->setRules([
        '@PER-CS' => true,
        '@Symfony' => true,
        'declare_strict_types' => true,

        // Override @Symfony
        'phpdoc_align' => [
            'align' => 'left',
            'tags' => [
                'method',
                'param',
                'property',
                'property-read',
                'property-write',
                'return',
                'throws',
                'type',
                'var',
            ],
        ],
        'phpdoc_separation' => [
            'groups' => [
                // Defaults
                ['deprecated', 'link', 'see', 'since'],
                ['author', 'copyright', 'license'],
                ['category', 'package', 'subpackage'],
                ['property', 'property-read', 'property-write'],

                // Overrides
                ['template', 'template-covariant', 'template-uses'],

                ['uses'],

                ['phpstan-*'], // This is not available... yet.

                ['phpstan-param', 'phpstan-return'],
            ],
        ],
        'global_namespace_import' => [
            'import_classes' => null,
            'import_constants' => true,
            'import_functions' => true,
        ],
        'no_empty_comment' => false,
        'single_line_throw' => false,
        'yoda_style' => false,
        'phpdoc_to_comment' => [
            'ignored_tags' => [
                'array',
                'var',
                'phpstan-var',
            ],
        ],
        ])
    ->setFinder(
        (new Finder())
            ->name('*.php')
            ->in(__DIR__.'/src')
            ->in(__DIR__.'/tests')
            ->ignoreDotFiles(true)
            ->ignoreVCSIgnored(true)
    );
```
