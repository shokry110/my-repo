# my-repo
Hello, Pulumi
import * as pulumi from "@pulumi/pulumi";
import * as github from "@pulumi/github";

// Create a new GitHub repository
const repo = new github.Repository("my-repo", {
    name: "my-repo",
    visibility: "public",
});

// Define a file in the repository
const repoFile = new github.RepositoryFile("my-file", {
    repository: repo.name,
    file: "README.md",
    content: "Hello, Pulumi!",
    commitMessage: "Initial commit",
});

// Export the repository URL
export const repoUrl = repo.htmlUrl;
import * as pulumi from "@pulumi/pulumi";
import * as github from "@pulumi/github";

// Create a new repository
const repo = new github.Repository("my-repo", {
    name: "my-new-repo",
    description: "This is my new repository",
    visibility: "public",
});

// Export the repository URL
export const repoUrl = repo.htmlUrl;

